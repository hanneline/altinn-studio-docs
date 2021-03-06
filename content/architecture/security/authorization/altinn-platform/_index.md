---
title: Authorization - Altinn Platform
description: Description of the Authorization Architecture for Altinn Platform
tags: ["architecture", "security"]
weight: 100
linktitle: Altinn Platform
alwaysopen: false
---

{{% notice warning %}}
NOTE: Work in progress. [See Github Issue](https://github.com/Altinn/altinn-studio/issues/963)
{{% /notice %}}

Altinn Platform has [attribute based access control (ABAC)](https://en.wikipedia.org/wiki/Attribute-based_access_control).
In short, request is authorized based on attributes for the request. Eg what data element is the user accessing, who owns it, 
what type of data element and so on.

The Authorization architecture in Altinn Platform are used as important components in authorization Architecture form Altinn Apps 

## Authorization Components
The authorization architecture for Altinn Platform are based on the 
[XACML reference architecture](https://en.wikipedia.org/wiki/XACML).

This architecture defines the following components.

### Policy Decision Point (PDP)
The Policy Decision Point is responsible for deciding if the requested operation is allowed.
PDP looks at the rules defined for a given resource, and based on roles or other claims it decides if
user or system is allowed to perform the request
[Learn about Policy Decision Point in Altinn Platform](pdp)

### Policy Information Point
The Policy Information Point is used by PDP to gather information needed to perform the decision.

[Learn about Policy Information Point in Altinn Platform](pip)

### Policy Administration Point
The policy administration point is where the rules are defined

[Learn about Policy Administration Point in Altinn Platform](pap)

### Policy Enforcment Point
The Policy Enforcment Point is where the user or system is actual stopped or allowed to perform a requested operation
on a resource. 

[Learn about Policy Enforcment Point in Altinn Platform](pdp)

### Policy Retrival Point
The policy retrieval point is where PDP can request the policies for a given
resource. 
[Learn about Policy Enforcment Point in Altinn Studio Apps](pdp)

### Context handler
The context handler is responsible for converting the resource ID to 
something that PDP can understand. 

[Learn about Policy Enforcment Point in Altinn Studio Apps](contexthandler)

The diagram below show the solution architecture where the different authorization functionality is located.

{{%excerpt%}}
<object data="/architecture/solution/altinn-apps/AltinnAppsEcosystem_SolutionArchitecture.svg" type="image/svg+xml" style="width: 100%;"></object>
{{% /excerpt%}}

## The Authorization Model
The authorization model is flexible.

[Learn about authorization model in Altinn Platform](model)

## The Overall Authorization flow
The sequence diagram below show how request are authorized

{{%excerpt%}}
<object data="/architecture/security/authorization/altinn-platform/AuthorizationFlow.svg" type="image/svg+xml" style="width: 100%;"></object>
{{% /excerpt%}}

### Example process

The following flow describes in detail the authorization processs when the REACT frontend calls a API to store form data

1. User press save in the REACT application. REACT application makes a http post request against the 
[ServiceAPIController](https://github.com/Altinn/altinn-studio/blob/master/src/AltinnCore/Runtime/Controllers/ServiceAPIController.css) in 
2. The configured Policy Enforcment Point for the API, the [Service Access Handler](https://github.com/Altinn/altinn-studio/blob/master/src/AltinnCore/Runtime/Authorization/ServiceAccessHandler.cs),  triggers to verify that user is authorized
3. The PEP identifies the authenticated user from authorizationhandler context and find the relevant resource ID from request
4. The PEP calls the PDP functionality in AltinnCore.Authorization application 
5. 

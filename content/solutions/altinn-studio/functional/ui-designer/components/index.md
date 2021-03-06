---
title: Available form components
description: Overview of the form components that are available for use
tags: ["ui-designer", "form-components"]
weight: 100
---

### Text components
<table>
  <tbody>
    <tr>
      <th>Component name</th>
      <th>Available properties</th>
      <th>Properties editor</th>
      <th>Default look</th>
    </tr>
    <tr>
      <td>Title</td>
      <td>
        <ul>
          <li>Title text</li>
          <li>Title type (H2, H3, H4)</li>
      </td>
      <td><img alt="Title component - edit properties" src="props-title.png?width=700" title="Title component - edit properties" /></td>
      <td><img alt="Title component - default look" src="display-title.png?width=700" title="Title component - default look" /></td>
    </tr>
    <tr>
      <td>Paragraph</td>
      <td>
        <ul>
          <li>Paragraph text</li>
      </td>
      <td><img alt="Paragraph component - edit properties" src="props-paragraph.png?width=700" title="Paragraph component - edit properties"/></td>
      <td><img alt="Paragraph component - default look" src="display-paragraph.png?width=700" title="Paragraph component - default look" /></td>
    </tr>
  </tbody>
</table>

### Basic form components

<table>
  <tbody>
    <tr>
      <th>Component name</th>
      <th>Available properties</th>
      <th>Properties editor</th>
      <th>Default look</th>
    </tr>
    <tr>
      <td>Input</td>
      <td>
        <ul>
          <li>Link to data model</li>
          <li>Label text</li>
          <li>Description text</li>
      </td>
      <td><img alt="Input component - edit properties" src="props-input.png?width=700" title="Input component - edit properties" /></td>
      <td><img alt="Input component - default look" src="display-input.png?width=700" title="Input component - default look" /></td>
    </tr>
    <tr>
      <td>Checkboxes</td>
      <td>
        <ul>
          <li>Link to data model</li>
          <li>Label text</li>
          <li>Description text</li>
          <li>Method to add options (codelist/manual)</li>
          <li>Codelist name
          <li>Manual option
            <ul>
              <li>Label
              <li>Value
            </ul>
          <li>Pre-selected choice
      </td>
      <td>
        Manual adding of options <br/>
        <img alt="Checkboxes component - edit properties" src="props-checkbox.png?width=700" title="Checkboxes component - edit properties"/><br/>
        Adding options via codelist <br/>
        <img alt="Checkboxes component - edit properties" src="props-checkbox-codelist.png?width=700" title="Checkboxes component - edit properties"/>
      </td>
      <td><img alt="Checkboxes component - default look" src="display-checkbox.png?width=700" title="Checkboxes component - default look" /></td>
    </tr>
    <tr>
      <td>Radio buttons</td>
      <td>
        <ul>
          <li>Link to data model</li>
          <li>Label text</li>
          <li>Description text</li>
          <li>Method to add options (codelist/manual)</li>
          <li>Codelist name
          <li>Manual option
            <ul>
              <li>Label
              <li>Value
            </ul>
          <li>Pre-selected choice
      </td>
      <td>
        Manual adding of options <br/>
        <img alt="Radio buttons component - edit properties" src="props-radio.png?width=700" title="Radio buttons component - edit properties"/><br/>
        Adding options via codelist <br/>
        <img alt="Radio buttons component - edit properties" src="props-radio-codelist.png?width=700" title="Radio buttons component - edit properties"/>
      </td>
      <td>
        <img alt="Radio buttons component - default look" src="display-radio.png?width=700" title="Radio buttons component - default look" />
      </td>
    </tr>
    <tr>
      <td>Text Area</td>
      <td>
        <ul>
          <li>Link to data model</li>
          <li>Label text</li>
          <li>Description text</li>
          <li>Read only</li>
      </td>
      <td><img alt="Text area component - edit properties" src="props-text-area.PNG?width=700" title="Text area component - edit properties" /></td>
      <td><img alt="Text area component - default look" src="display-text-area.PNG?width=700" title="Text area component - default look" /></td>
    </tr>
  </tbody>
</table>

In addition to the above components, the following basic form components are under development. These are not ready to be used, they will be added to the overview when they are ready to use:

* Dropdown
* File attachment
* Container

### Advanced form components
Advanced form components are components that potentially contain multiple fields that each need to be mapped to a field in the data model. They will typically contain fields that are functionally related, ex. fields related to _address_, see below.

{{% notice info %}}
NOTE: The address component is a proof of concept. The content/design of this component and its configuration is under development. The component is available for use, but might undergo major changes in the future.
{{% /notice %}}

<table>
  <tbody>
    <tr>
      <th>Component name</th>
      <th>Available properties</th>
      <th>Properties editor</th>
      <th>Default look</th>
    </tr>
    <tr>
      <td>Address component<br/> (simple mode)</td>
      <td>
        <ul>
          <li>Link to data model for field:</li>
            <ul>
              <li>Address
              <li>Postal code
              <li>Postal area
            </ul>
          <li>Label text for Address field
      </td>
      <td><img alt="Address (simple mode) - edit properties" src="props-address-simple.png?width=700" title="Address (simple mode) - edit properties" /></td>
      <td><img alt="Address (simple mode) - default look" src="display-address-simple.png?width=700" title="Address (simple mode) - default look" /></td>
    </tr>
    <tr>
      <td>Address component<br/> (advanced mode)</td>
      <td>
        <ul>
          <li>Link to data model for field:</li>
            <ul>
              <li>Address
              <li>Postal code
              <li>Postal area
              <li>C/O
              <li>Housing number
            </ul>
          <li>Label text for Address field
      </td>
      <td><img alt="Address (advanced mode) - edit properties" src="props-address-advanced.png?width=700" title="Address (advanced mode) - edit properties" /></td>
      <td><img alt="Address (advanced mode) - default look" src="display-address-advanced.png?width=700" title="Address (advanced mode) - default look" /></td>
    </tr>
  </tbody>
</table>

### Custom / third party components
If there is a need for specialized/custom components, it is possible to use components that are not part of the Altinn Studio component library. These components need to be written in React, and imported to the service. See [here]() for instructions on how to create a custom component using React.

#### Adding a custom component to a service
The custom component needs to be defined in a _index.js_-file. This file can then be included in the service repository. To make the component available to the service, create a file called `ThirdPartyComponents.json` in the service repository, under the `Resources` folder. 

{{% notice info %}}
NOTE: It is important that the name and location of the file _ThirdPartyComponents.json_ is correct, otherwise the component will not be available for the service.
{{% /notice %}}

The content of this file should be as follows:

```
{
  "packages": [{
    "packageName": "[name of the component]",
    "location": "[Link to raw format of index.js in service repository]"
  }]
}
```

- `[name of the component]` should be replaced with the name that will be shown in the Altinn Studio UI editor. 
- `[Link to raw format of index.js in service repository]` should be replaced with the full url to the file in the git repo (can be found by navigating to the file in the [Repositories] solution and copying the url).

Once this is done, the UI editor in Altinn Studio should be re-loaded, and the custom component will appear in the component menu on the left.

{{% notice info %}}
NOTE: Editing properties for custom components in the UI editor is currently not supported. As such, and properties for the component should be set directly in the code for the component. The documentation will be updated once this functionality is made available through the UI editor. 
{{% /notice %}}
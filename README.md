ionic-Select-Control
====================

## Description

This is a customizable select box for ionic framework.
While the package name is "ionic-select-control", the module name is "$selectBox".

## Dependencies

This component uses ionic-modal and ionic-list from ionic framework components.
Clicking outside the modal won't close it.

## How to use

1. Install with bower:

`bower install ionic-select-control --save`

2. Include as a dependency of your angular module:

```javascript
angular.module('myApp', ['ionic', '$selectBox'])
```

3. Include necessary files in your index.html header, for example linking directly to files where bower component was installed:

```HTML
   <link rel="stylesheet" href="lib/ionic-select-control/dist/SelectBox.min.css" >

   <script type="text/javascript" src="lib/ionic-select-control/dist/SelectBox.min.js"></script>
```

4. Use the select-box directive:

```HTML
  <select-box ng-Selected-Value="selectedValue"
          		ng-Item-Name="label"
          		ng-Item-Id="id"
          		ng-title="Select something!"
          		ng-data="mySelectedValue"
          		ng-placeholder="nothing selected!"
          		ng-select-changed="doSomethingWithSelectedValue(selectedValue)"
          		ng-placeholder-class="myPlaceholderStyle"
				ngHtmlName="optionalHiddenFieldName"
				ngIsRequired="true"
				ngPopup=true
				ngPopupClass="myIonicPopupClass"
          		>

</select-box>
```
 
### Directive parameters
| Name | Description |Remark |
| :------------- | :------------- | :------------- |
|ng-Selected-Value|Scope variable that will get populated with selected option value|Required. <br> Updated using two-way binding. It is the internal ng-model of the component's hidden field.|
|ng-data|Scope object passed to SelectBox, format: list of object with two properties, one for label, one for value|Required.|
|ng-Item-Name|Name of property for label, in scope object passed to SelectBox|Required.|
|ng-Item-Id|Name of property for value, in scope object passed to SelectBox|Required.|
|ng-placeholder|Placeholder string when no value is selected|Required.|
|ng-title|Title of SelectBox|Required.|
|ng-select-changed|JS function to execute after item selection.|Optional. <br> This function argument name should be 'selectedValue', both in your controller function declaration and in SelectBox ng-select-changed attribute value (function call).|
|ng-placeholder-class|CSS class to apply to placeholder|Optional.|
|ng-select-box-class|CSS class to apply to whole select box control|Optional.|
|ngHtmlName|String.<br>Allows you to bind an name attribute on the hidden input (useful for form validation)|Optional.|
|ngIsRequired|Boolean, truthy.<br>Allows you to make the hidden input required (useful for form validation)|Optional.|
|ngPopup|Boolean, truthy.<br>Allows using ionicPopup service instead of ionicModal (it is more elegant for some cases)|Optional.|
|ngPopupClass|String.<br>Allows you to bind CSS classes to the ionicPopup configuration|Optional.|

 **Example of object for ng-data:**
 ```javascript
var obj = [
  {label: "Value1", id:"1"},
  {label: "Value2", id:"2"},
  {label: "Value3", id:"3"},
  {label: "Value4", id:"4"}
]
 ```

## Tests

In "test" root folder, there are some html test pages with different configurations, stylings. 
They don't require a web server to be opened, thus are kept basic.
Used libraries (ionic bundle, angular translate) are stored in "lib" root folder.

## History

### Version 1.10.0
- Merged pull request "Fix stuck placeholder in Safari 11 /iOS 11. Support popup-class for modal mode too." Thanks again [amplexdenmark](https://github.com/amplexdenmark).

### Versions 1.9.0, 1.9.1
- Merged pull request "HTML field name, required attr, popup alternative, popup class". Thanks [aless673](https://github.com/aless673). Updated Readme.md.

### Version 1.8.1
- Merged pull request "Make sure it works from a popup, popover, modal". Thanks [amplexdenmark](https://github.com/amplexdenmark).

### Version 1.8.0
- Added whole component styling option.

### Version 1.7.0
- Added placeholder styling option.

### Version 1.6.1
- Fixed "main" section in bower.json.

### Version 1.6.0
- Added support for external change value Thanks [ivomans](https://github.com/ivomans).
- Improved Readme.

### Version 1.5.3
- Added a "main" section in bower.json (support for main-bower-files gulp plugin).

### Version 1.5.2
- Added ability to clear selection when setting null value to scope object associated to "ng-Selected-Value" selectBox attribute.
- Regression in version 1.5.0 fixed in 1.5.2, please don't use 1.5.0.

### Version 1.4.0
- Added Gulp tasks to minify and uglify source and stylesheet.

### Version 1.3.0
- Disallow modal closing when clicking outside the modal.

### Version 1.2.0
- Fixed javascript error when destroying scope without opening modal ($scope.modal undefined).

### Version 1.1.0
- Component properly refreshes when scope changes.
- Test pages reworked.
- Readme fix and improvement.

### Versions 1.0.1 and 1.0.2
- MIT license added + Readme fix.

### Version 1.0.0
 - Addition of ng-select-changed attribute to hook a function to handle selected value. (postb99 new fork, from dslack fork).
 - Added Header class support to better integrate with apps (dslack fork).

## Contributors
- Project creator: [domiSchenk](https://github.com/domiSchenk)
- Fork and current maintainer: [postb99@OSAMES](https://github.com/postb99)
- Merged pull requests: [ivomans](https://github.com/ivomans), [amplexdenmark](https://github.com/amplexdenmark), [aless673](https://github.com/aless673)

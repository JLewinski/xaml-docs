---
title: Content Controls (Structured Document Tags) 
page_title: Content Controls
description: This article describes which content controls are supported in RadRichTextBox
slug: radrichtextbox-features-content-controls
tags: content controls, richtextbox
published: True
---

# Content Controls (Structured Document Tags)

Structured Document Tags (sdt) enable users to add specific semantics to part of the document: restricting input, modifying editing behavior etc. 

>note Currently, RadRichTextBox only visualizes the value of the content controls and there is no UI that allow you to interact with them. The import and export operations will work with Office Open XML (docx) and XAML formats. When exporting to other formats the content controls will be lost, however their content (current value) will be exported.

## Content Controls Inside the Document

The contented controls can be defined on __Block__, __Inline__, __Row__ or __Cell__ level. They can be nested inside each other as well. In addition, one can modify the editing behavior of the content controls. This means that you can lock the content of the content control, the entire content control or both.

## Supported Content Controls 

* __Bibliography__
* __CheckBox__
* __Citation__
* __ComboBox__
* __Date__
* __DocumentPart__
* __DocumentPartGallery__
* __DropDownList__ 
* __Equation__
* __Group__
* __Picture__
* __RichText__
* __Text__
* __PlaceHolder__
* __RepeatingSection__
* __RepeatingSectionItem__

The following content controls are not supported by __Microsoft Word__:  
* __Bibliography__
* __Equation__

## Common Content Controls Properties
 
The above content controls share the following properties: 

* __Type:__ The type of the current content control. 
* __ID:__ Each content control must have a an unique ID.
* __DataBinding:__ Gets or sets an XML mapping (DataBinding) that relates the content of associated SDT to a specific XML node.
* __Lock:__ This property controls if the entire content control or its contents can be edited or deleted. The possible values are:
    - __Unlocked:__ The content control can be edited and deleted. 
    - __SdtLocked:__ The content control can be edited but cannot be deleted.
    - __ContentLocked:__ The content control cannot be edited, the entire content control can be deleted.
    - __SdtContentLocked:__ The content control cannot be edited or deleted. 
* __Alias:__ Gets or sets the name for the associated content control (this is necessary because the properties are stored in a separate object).
* __OutlineColor:__ Gets or sets the color that is used for visualizing the outline.
* __OutlineAppearance:__ Represents the different options for visualizing the outline of a content control.The possible values are:
    - __BoundingBoxes:__ The content is wrapped in a bounding box that may also contain a specific editor.
    - __Tags:__ The content is wrapped in design view tag.
    - __None:__ The content does not have outline visualization.



## Content Controls with Specific Properties

### CheckBox

The __CheckBox__ content control exposes two properties __CheckedState__ and __UnCheckedState__. Both properties are of type __SdtCheckBoxState__ which allows you to set the respective character and its font. The __Checked__ property specifies whether the checkbox is checked.

### ComboBox and DropDownList

The __ComboBox__ and __DropDownList__ provide the user with options to choose from. The only difference is that when using ComboBox you can add a value that is not in the data source.
* __Items:__ This property allows you to specify the predefined items. 
* __LastValue:__ This property returns the currently selected value. 

### Date

The __Date__ content control allows you to enter a date by using a calendar. The date content control has the following properties:
* __DateFormat:__ Allows you to get/set the format string of the date. If it is omitted the default date format for the language is used.
* __LanguageId:__ Allows you to get/set the CultureInfo object for the date format.
* __DateTime:__ The current selected date, stored as string. 
* __Calendar:__ Allows you to select the calendar type.     


# See Also
* [Working with Content Controls]({%slug radrichtextbox-features-working-with-content-controls%})
---
title: Visual Structure
page_title: .NET MAUI Date Picker Documentation | Date Picker Visual Structure
description: Check our &quot;Visual Structure&quot; documentation article for Telerik Date Picker for .NET MAUI.
position: 0
slug: date-picker-visual-structure
---

# Visual Structure

Here are described all visual elements used in the Date Picker for .NET MAUI.

## Date Picker Structure before and after a date/time is selected

![Date Picker Visual Structure](images/date_picker_placeholder_display.png "Visual elements of Date Picker control")

## Picker Popup Visual Structure

![Date Picker Popup Visual Structure](images/date_picker_structure.png "Visual elements of Date Picker Popup")

## Legend ##

- **Placeholder** - the text visualized before picking a date/time. Placeholder could be customized through the [PlaceholderTemplate]({%slug date-picker-templates%}#placeholdertemplate) property.
- **DisplayStringFormat** - the text vislualized after a date/time is picked.
- **Header** - the text displayed in the popup header. It could be set a direct text through the [HeaderLabelText]({%slug date-picker-styling%}#styling) property or fully customize the popup header using the [HeaderTemplate]({%slug date-picker-templates%}#headertemplate) property.
- **SpinnerHeader** - the text visualized for spinner header depending on the values to be picked. For example if the `SpinnerFormatString` is *d* the text visualized for spinner header will be **Month** **Day** **Year**.
- **Spinner** - displays items in a list.
- **SelectionHighlight** - highlight the current selected date when the popup is open.
- **Footer** - the footer of the popup. By default is contains OK and Cancel Buttons. It could be customized through the [FooterTemplate]({%slug date-picker-templates%}#footertemplate) property.
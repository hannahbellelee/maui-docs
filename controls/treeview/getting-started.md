---
title: Getting Started
page_title: .NET MAUI TreeView Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI TreeView and add the control to your .NET MAUI project."
position: 1
slug: treeview-getting-started
---

# Getting Started with the .NET MAUI TreeView

This guide provides the information you need to start using the [Telerik UI for .NET MAUI TreeView]({%slug treeview-overview%}) by adding the control to your project.

At the end, you will be able to achieve the following result on Desktop platforms.

![TreeView Getting Started](images/treeview-gettingstarted-desktop.png)

And the result on mobile platforms:

![TreeView Getting Started](images/treeview-getingstarted-mobile.png)


## Prerequisites

Before adding the TreeView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a TreeView control to your page. The following example shows a sample TreeView definition populated with sample data.

  The TreeView provides UI virtualization, which requires the visual parent to provide vertical or horizontal space. To avoid breaking UI virtualization or gesture mechanisms:

  * Do not place the TreeView inside a `StackLayout` or inside a `ScrollView`.
  * Do not set the TreeView to a `RowDefinition Height="Auto"` Grid definition.

**1.** Set up the `RadTreeView` instance:

<snippet id='treeview-getting-started-xaml' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** reate sample `Item` class:

<snippet id='treeview-getting-started-item' />

**4.** Add `ViewModel` class:

<snippet id='treeview-getting-started-viewmodel' />

Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
}           
```

>important For the TreeView Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) Treeview -> Getting Started category.

## Additional Resources

- [.NET MAUI TreeView Product Page](https://www.telerik.com/maui-ui/treeview)
- [.NET MAUI TreeView Forum Page](https://www.telerik.com/forums/maui?tagId=1829)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [Scrolling]({%slug treeview-scrolling%})
* [Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Commands]({%slug treeview-commands%})
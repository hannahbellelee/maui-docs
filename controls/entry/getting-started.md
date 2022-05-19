---
title: Getting Started
page_title: .NET MAUI Entry Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI Entry control and add the control to your .NET MAUI project."
position: 1
previous_url: /controls/entry/entry-getting-started
slug: entry-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Entry by adding the control to your project.

At the end, you will be able to achieve the following result.

![Entry Getting Started Example](images/entry_getting_started.png)

## Prerequisites

Before adding the Entry, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add an Entry control to your page.

 <snippet id='entry-getting-started-xaml' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})
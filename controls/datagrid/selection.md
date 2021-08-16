---
title: Selection
page_title: .NET MAUI DataGrid Documentation | Selection
description: Check our &quot;Selection&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 3
slug: datagrid-selection-overview
---

# Selection

**RadDataGrid** exposes a selection feature - users can select a cell or a row by tapping on it. To cancel the selection, they can simply tap on the cell or a row again. The control provides single and multiple selection.

This article explains the basic properties and methods that RadDataGrid provides for working with selection.

## Important Properties

RadDataGrid supports different selection modes that you can modify through the [**SelectionUnit**](#selectionunit) and [**SelectedItems**](#selecteditems) properties. Before you can set the [**SelectionMode**](#selectionmode), you must choose which Unit can be selected.

### SelectionUnit

The **SelectionUnit** property (type of *Telerik.XamarinForms.DataGrid.DataGridSelectionUnit*) allows you to control which Unit can be selected:

* **Row**: The unit to select is a grid row (by default).
* **Cell**: The unit to select is a cell within a grid row.

  >note To define a Cell when using a selection, you can use the DataGridCellInfo class that holds all the information about the Cell. To define a Row when using a selection, you can use your data object.

The example below shows how to set **SelectionUnit** in XAML and code-behind:

```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
							 SelectionUnit="Cell" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionUnit = Telerik.XamarinForms.DataGrid.DataGridSelectionUnit.Cell;
```

### SelectionMode

The **SelectionMode** property (type of *Telerik.XamarinForms.DataGrid.DataGridSelectionMode*) provides the following modes:

* **Single**: Single unit may be selected(by default).
* **Multiple**: Multiple units may be selected.
* **None**: No selection is allowed.

The example below shows how to set **SelectionMode** in XAML and code-behind:

```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
							 SelectionMode="Multiple" />
```
```C#
var dataGrid = new RadDataGrid();
dataGrid.SelectionMode = Telerik.XamarinForms.DataGrid.DataGridSelectionMode.Multiple;
```

### SelectedItems

Once you make a selection, you can get or modify the collection with the selected Items by using the **SelectedItems** property:

* **SelectedItems** property (type of *ObservableCollection&lt;object&gt;*): Gets or Modifies an ObservableCollection of the currently selected Items (their type depends on the applied SelectionUnit, that is, DataGridCellInfo for Cell and Data Item for Row).

>note You can listen to the CollectionChanged event of the SelectedItems directly.

## Events

- **SelectionChanged**: An event that is triggered whenever the SelectedItems collection is changed. The SelectionChanged event handler receives two parameters:
	* The sender argument, which is of type object, but can be cast to the __RadDataGrid__ type.
	* A __DataGridSelectionChangedEventArgs__ object, which provides the following properties:
		- RemovedItems - gets a list of the removed items from the SelectedItems collection.
		- AddedItems - gets a list of the added items to the SelectedItems collection.

## Methods

Additional functionalities for programmatic selecting and deselecting items are exposed by RadDataGrid as methods. They also depend on the applied **SelectionUnit**.

#### Methods for programmatic selection when SelectionUnit is "Row":

* **SelectItem**(object item): Selects the specified data item and adds it in the SelectedItems collection.
* **DeselectItem**(object item): Removes the selection for the specified data item and removes it from the SelectedItems collection.

#### Methods for programmatic selection when SelectionUnit is "Cell":

* **SelectCell**(DataGridCellInfo item): Selects the grid cell as defined by the specified cell info.
* **DeselectCell**(DataGridCellInfo item): Removes the selection for the grid cell defined by the specified cell info.

#### Methods for programmatic selection of all items

* **SelectAll**(): Selects all the items as defined when SelectionMode is "Multiple".
* **DeselectAll**(): Clears the current selected items as defined by the SelectionUnit property.

### Example
In order to illustrate how these methods can be used, let's have the following example:

1) Add a sample business object:

```XAML
public class Person
{
	public string Name { get; set; }
	public int Age { get; set; }
	public string Department { get; set; }
}
```

2) Add a ViewModel with a list of "Person" objects:

```C#
public class ViewModel
{
	public ViewModel()
	{
		this.People = new ObservableCollection<Person>()
		{
			new Person { Name = "Kiko", Age = 23, Department = "Production" },
			new Person { Name = "Jerry", Age = 23, Department = "Accounting and Finance"},
			new Person { Name = "Ethan", Age = 51, Department = "Marketing" },
			new Person { Name = "Isabella", Age = 25, Department = "Marketing" },
			new Person { Name = "Joshua", Age = 45, Department = "Production" },
			new Person { Name = "Logan", Age = 26, Department = "Production"},
			new Person { Name = "Aaron", Age = 32, Department = "Production" },
			new Person { Name = "Elena", Age = 37, Department = "Accounting and Finance"},
			new Person { Name = "Ross", Age = 30, Department = "Marketing" },
		};
	}

	public ObservableCollection<Person> People { get; set; }
}
```

3) Add the RadDataGrid definition:

```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
						  ItemsSource="{Binding People}" />
```

4) Set the ViewModel class as a BindingContext:

```C#
this.BindingContext = new ViewModel();
```

Now you use various approaches to select the first employee from the Marketing department. Each snippet shows a possible approach:

* In the case of Row selection, use SelectItem method:

```C#
var firstMarketingItem = ((ObservableCollection<Person>)this.dataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.dataGrid.SelectItem(firstMarketingItem);
```

* For Cell selection, use SelectCell method - it takes as a parameter a **DataGridCellInfo** object. DataGridCellInfo object can be easily created using the needed data item (of type Person in our case) and setting the column corresponding to the cell you'd need to select.

```C#
var firstMarketingCell = ((ObservableCollection<Person>)this.dataGrid.ItemsSource).First(p => p.Department == "Marketing");
this.dataGrid.SelectCell(new DataGridCellInfo(firstMarketingCell, this.dataGrid.Columns[2]));
```

* Lastly, you call the SelectAll/DeselectAll method like this:

```C#
this.dataGrid.SelectAll();
```

## See Also

* [DataGrid Sorting]({%slug datagrid-sorting-overview%})
* [DataGrid Commands]({%slug datagrid-commands-overview%})
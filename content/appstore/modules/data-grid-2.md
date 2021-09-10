---
title: "Data Grid 2"
category: "Modules"
description: "Describes the configuration and usage of the Data Grid 2 module, which is available in the Mendix Marketplace."
tags: ["marketplace", "marketplace component", "data grid", "platform support"]
#If moving or renaming this doc file, implement a temporary redirect and let the respective team know they should update the URL in the product. See Mapping to Products for more details.
---

## 1 Introduction

[Data Grid 2](https://marketplace.mendix.com/link/component/116540) is the successor to the standard data grid widget for displaying content in a tabular form. It comes with many powerful new features and settings like support for widgets, row and cell coloring, responsive layout, accessibility, and different paging options like virtual scrolling. It offers personalization support so that end-users can show, hide, and re-order columns. Personalizations can be persisted in the database for flexibility and control. The data grid is packaged as a module and uses a flexible approach for filtering. Developers can drag and drop data-grid-specific widgets inside the header of the grid and tailor the behavior of the filters. This module includes filters for text, numbers, dates, and the option to add drop-down filters for single or multiple selections.

Here is an example of a data grid using filters:

![Example of data grid using filters](attachments/data-grid-2/example.png)

### 1.2 Advanced Options

The data grid has an option to enable advanced options. When toggle this option on, it enables numerous features to customize your data grid:

* Pagination type
* Pagination position
* Empty list option
* Dynamic row and cell class
* Column capabilities
* Custom configuration

## 2 Capabilities

In the new data grid, you are able to choose how users can iterate within the grid. Iteration capabilities are listed below.

### 2.1 Sorting

**Sorting** enables the header to be clickable. When clicked it will switch between ascending, descending, and no sorting. This functionality can be discerned according to the arrows on the right side:

* Arrow up: ascending sorting applied
* Arrow down: descending sorting applied
* Double-sided arrow: no sorting is applied

![Ascending sort](attachments/data-grid-2/sorting-asc.png)
![Descending sort](attachments/data-grid-2/sorting-desc.png)
![Natural order (No sorting)](attachments/data-grid-2/no-sorting.png)

### 2.2 Resizing

**Resizing** enables the header to be resizable by dragging the handle on the right side of a header. Here is an example of the handle indicating the column is resizable:

![Handle indicating the column is resizable](attachments/data-grid-2/resizing.png)

### 2.3 Reordering

**Reordering** enables the header to be reordered by dragging and dropping in another column. When dragging, a black handle indicates where the column can be dropped:

Here is an example of reordering in progress:

![Example of reordering](attachments/data-grid-2/reordering.gif)

### 2.4 Hiding

**Hiding** enables a column to be hidden. When this option is enabled for any column, a button with an eye icon will appear on the right side of the data grid like the example below. It contains all the columns **hidden by default** or enabled to be hidden. When de-selected, the column will not be visible in the grid anymore.

Here is an example of hiding button containing columns to be hidden:

![Example of hiding button containing columns to be hidden](attachments/data-grid-2/hiding.png)

{{% alert type="info" %}}
When a column is marked as “Yes, hidden by default” it will render differently in Structure mode and Design mode (Studio Pro) and in Studio to indicate that the column is hidden. **When running the application, the column will in fact be hidden by default**.
{{% /alert %}}

Here is an example containing a column with **Yes, hidden by default** in Structure mode:

![Example containing a column with “Yes, hidden by default” in Structure mode](attachments/data-grid-2/hidden-columns-structure-mode.png)

Here is an example containing a column with **Yes, hidden by default** in Design mode and Studio:

![Example containing a column with “Yes, hidden by default” in Design mode and Studio](attachments/data-grid-2/hidden-columns-design-mode.png)

## 3 Pagination

In the new data grid we offer two types of pagination: **Paging Buttons** and **Virtual Scrolling**.

### 3.1 Paging Buttons

The **Paging Buttons** option will render the default buttons as the previous data grid. When the data source is uncountable (like entities in Data Hub) neither the last page button nor the counting will be be available. The paging can be positioned above or below the grid:

![Example of paging buttons](attachments/data-grid-2/paging-buttons.png)

### 3.2 Virtual Scrolling 

The **Virtual Scrolling** option forces the data grid to show a fixed amount of items (defined in the page size option) within a scrollable container. When the end-user reaches the bottom of the scrollable container it fetches more items automatically.

## 4 Columns

In Data Grid you can choose what you want to render into columns. This can be an attribute, dynamic text, or even a combination of widgets (custom content). To choose what you want to render, open a column in the column list and select the appropriate option according to your needs.

Here is an example of column properties:

![Example of column properties](attachments/data-grid-2/column-properties.png)

### 4.1 Attribute

**Attribute** renders the value of a selected attribute.

### 4.2 Dynamic Text

**Dynamic Text** renders a text-templated string which can contain text combined with attributes:

![Example of dynamic text](attachments/data-grid-2/column-dynamic-text.png)

### 4.3 Custom Content

**Custom Content** allows users to drop widgets into the data grid and use the column attribute value to show custom content. After selecting this option you will be given dropzones in which to drop your widgets.

Here is an example of custom content using new Badge widget in Structure mode:

![Example of custom content using new Badge widget in Structure mode](attachments/data-grid-2/column-custom-content.png)

### 4.4 Column Width

You can define how each cell will be rendered in the data grid. We offer three choices:

![Settings for column width for each column item](attachments/data-grid-2/column-width.png)

* **Auto-fill** — With this option it will auto define the width of your column, if all columns are using auto-fill, it will divide evenly the same width, if another column is configured with auto-fit or manual, it will fill the available space.
* **Auto-fit** — Content With this option it will calculate the width of your column based on the content of each row.
* **Manual** — With this option you will manually define the size of your column based of flexbox grow values, for more information, please [check here](https://www.w3.org/TR/css-flexbox-1/).

### 4.5 Alignment

You can choose how the content inside your columns will be aligned. We offer three choices: left, center, and right.

{{% alert type="info" %}}
This will also change the alignment of your header.
{{% /alert %}}

![Settings for alignment of each column item](attachments/data-grid-2/column-alignment.png)

### 4.6 Dynamic Cell Class

In the new data grid we offer an option to dynamically apply a CSS class in a specific cell. You can achieve this by adding an expression based on the column value (attribute) like the example below.

In this example we check the value of `StringAttribute` and then apply the class `.my-name-class` if the attribute is equal to `my name` to the cell:

![Example of dynamic cell class](attachments/data-grid-2/dynamic-cell-class.png)

## 5 Rows

This section defines options for the rows of the grid.

### 5.1 Empty List Message

The **Empty List Message** option defines what users can see when the data grid does not have a value to be presented or when a filter is applied without results. When this option is defined as custom you can place widgets right above the rows in a dropzone. Here is an example:

![Example of empty list message placeholder in Structure mode](attachments/data-grid-2/empty-list-message.png)

### 5.2 Dynamic Row Class

The **Dynamic Row Class** option allows users to dynamically apply a CSS class in a specific row. This option will apply for the entire row the same class. You can achieve this by adding an expression based on the column value (attribute), like the example below.

{{% alert type="warning" %}}
If you have a dynamic cell class being applied it will have precedence over the row class.
{{% /alert %}}

In this example we check the value of `StringAttribute and` then apply the class `.my-name-class` if the attribute is equal to `my name` to the row:

![Example of dynamic row class](attachments/data-grid-2/dynamic-row-class.png)

## 6 Events

The new data grid can trigger some events while iterating with it.

### 6.1 On Click Action

Triggers an action (such as a nanoflow, microflow, or Show page action) when the end-user clicks in one of the rows. It also adds a pointer cursor to signal that it is clickable. This function also complies with accessibility features and can be reached using only the keyboard.

## 7 Filters

Sets of filters can be used in combination with data grids. To be able to use filters you need to select the option **Show column filters**. When this option is selected a drop-zone where you can place your desired filter widget will appear in each column header.

{{% alert type="warning" %}}
The type of your selected attribute should match the filter type. For example, a **Text filter** should be used for a String attribute. Also the desired attribute should be filterable (for example, not computed in a microflow).
{{% /alert %}}

![Settings for data grid 2](attachments/data-grid-2/settings-show-column-filters.png)

Here is an example of dropzones for filters in Structure mode:

![Example of dropzones for filters in Structure mode](attachments/data-grid-2/dropzones-for-filters.png)

### 7.1 Date Filter

![Example of  default Date filter look & feel](attachments/data-grid-2/date-filter.png)

**Date filter** allows users to match date attributes based on these predefined criteria:

* Greater than
* Greater than or equal
* Equal
* Not equal
* Smaller than
* Smaller than or equal

You can select your filter criteria in the Date Filter settings:

![Date filter settings](attachments/data-grid-2/date-filter-settings.png)

When **Adjustable by user** is defined as **No** it will not render the option to choose the filter type in the widget.

Here is an example of available filter types for **Date Filter**:

![Filter types for Date Filter](attachments/data-grid-2/date-filter-types.png)

Here is an example of **Date Filter** with **Adjustable by user** defined as **No**:

![Example of Date filter with “Adjustable by user” set as No](attachments/data-grid-2/date-filter-not-adjustable.png)

You can also define the default value of the widget which will be predefined as initial value when opening your data grid page.

### 7.2 Drop-Down Filter

![Example of default drop-down filter](attachments/data-grid-2/dropdown-filter.png)

**Drop-down filter** allows users to match enumeration values or a Boolean attribute. To configure the available options when you press the drop-down filter, you can manually add them in the options list or select **Automatic options** to automatically load the values:

![Example of settings for drop-down filter](attachments/data-grid-2/dropdown-filter-settings.png)

When adding a new option, the following properties are required:

* **Caption** — The text being rendered for each option in the drop-down.
* **Value** — The corresponding value that will be compared, if a value is being compared with an enumeration, it should match exactly the enumeration value. This property allows the usage of expression (you can use conditionals to apply dynamic values).

![Example of settings for new option](attachments/data-grid-2/dropdown-filter-item.png)

This widget also allows multiple selections by selecting **Multiselect** in the settings. Multiple selections can look like this:

![Example of multi select drop-down filter](attachments/data-grid-2/dropdown-filter-multiselect.png)

You can also define the empty option caption, which will be rendered as the first item if **Multiselect** if set as **No**. It allows users to clean the filter if pressed.

### 7.3 Number Filter

![Example of default number filter](attachments/data-grid-2/number-filter.png)

The **Number filter** allows users to match decimal, integer, and long attributes based on these predefined criteria:

* Greater than
* Greater than or equal
* Equal
* Not equal
* Smaller than
* Smaller than or equal

You can select your filter criteria in the **Number Filter** settings:

![Number filter settings](attachments/data-grid-2/number-filter-settings.png)

When **Adjustable by user** is defined as **No** it will not render the option to choose the filter type in the widget.

Here is an example of available filter types for **Number Filter**:

![Filter types for number filter](attachments/data-grid-2/number-filter-types.png)

Here is an example of **Number Filter** with **Adjustable by user** set as **No**:

![Example of number filter with “Adjustable by user” set as No](attachments/data-grid-2/number-filter-not-adjustable.png)

You can also define the default value of the widget, which will be predefined as initial value when opening your data grid page.

To have better control of when the filter will be applied, we offer a **Apply after (ms)** option under the **On change behavior** group. This option will only trigger the filter after a predefined period of time while typing. By default, we suggest 500ms.

### 7.4 Text Filter

![Example of default text filter](attachments/data-grid-2/text-filter.png)

**Text filter** allows users to match string attributes based on these predefined criteria:

* Contains
* Starts with
* Ends with
* Greater than
* Greater than or equal
* Equal
* Not equal
* Smaller than
* Smaller than or equal

You can select your filter criteria in the **Text filter** settings:

![Text filter settings](attachments/data-grid-2/text-filter-settings.png)

When **Adjustable by user** is defined as **No** it will not render the option to choose the filter type in the widget.

Here is an example of available filter types for **Text Filter**:

![Filter types for text filter](attachments/data-grid-2/text-filter-types.png)

Here is an example of Text Filter with **Adjustable by user** set to **No**:

![Example of text filter with “Adjustable by user” set as No](attachments/data-grid-2/text-filter-not-adjustable.png)

You can also define the default value of the widget, which will be predefined as initial value when opening your data grid page.

To have better control of when the filter will be applied, we offer a **Apply after (ms)** option under the **On change behavior** group. This option will only trigger the filter after a predefined period of time while typing. By default, we suggest 500ms.

## 8 Configuration

You can define an attribute to store the current configuration of the data grid. In this way, if you re-open your page then the current sorted columns, order, and hidden columns will remain the same as in the previous state. To set this option, you need to select a `String` attribute with `Unlimited` as its size as the attribute in the data grid **Personalization** tab in Studio Pro or **Configuration** in Studio.

{{% alert type="warning" %}}
If the desired `String` attribute does not contain `Unlimited` in its size, the Data grid will not be able to save all the configurations as expected.
{{% /alert %}}

Here is an example of an unlimited string attribute:

![Example of unlimited string attribute](attachments/data-grid-2/unlimited-string-attribute.png)

In order to select an attribute, you need to surround the new Data grid with a Data view. This will allow you to select an attribute. You can also define an action when the attribute will be updated with the new configurations.

Here is an example of a configuration containing an On change action:

![Example of a configuration containing on change action](attachments/data-grid-2/configuration.png)

## 9 Performance

The performance of the new data grid can be affected if sorting or filtering are enabled. This is because Data Grid 2 v1.1.0 retrieves all available values to do the sorting or filtering while the widget runs.

## 10 Troubleshooting

If you are using Atlas v2.x and you cannot upgrade to Atlas 3 at the moment, please replace the line 3 `cssFiles` with the following code in the file `theme/settings.json`:

```json
"cssFiles": [ 
    "styles/web/css/main.css", 
    "theme.compiled.css" 
],
```

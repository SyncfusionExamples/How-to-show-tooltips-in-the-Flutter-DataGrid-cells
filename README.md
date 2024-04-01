# How to show tooltips in the Flutter DataGrid cells.

In this article, you can learn about how to show tooltips in the Flutter DataGrid cells.

Initialize the [SfDataGrid](https://pub.dev/documentation/syncfusion_flutter_datagrid/latest/datagrid/SfDataGrid-class.html) widget with all the required properties. To achieve this, you can wrap the [Tooltip](https://api.flutter.dev/flutter/material/Tooltip-class.html) widget around the widget loaded in the DataGridCell and set the desired value in the [Tooltip.message](https://api.flutter.dev/flutter/material/Tooltip/message.html) property within the DataGridSource.buildRow method.

```dart
class EmployeeDataSource extends DataGridSource {

…
 
 @override
 DataGridRowAdapter buildRow(DataGridRow row) {
    return DataGridRowAdapter(
        cells: row.getCells().map<Widget>((e) {
      return Tooltip(
        message: 'Employee ${row.getCells()[1].value} Data',
        child: Container(
          alignment: Alignment.center,
          padding: const EdgeInsets.all(8.0),
          child: Text(e.value.toString()),
        ),
      );
    }).toList());
  }
}
```

You can download the example from [GitHub](https://github.com/SyncfusionExamples/How-to-show-tooltips-in-the-Flutter-DataGrid-cells)
# Adding a data source

To create a new data source, you will need to navigate to the 'Dashboards' page.

![Dashboard menu](/images/menu-dashboard.png)

Once on the dashboard page click the ![Add data source](/images/add-datasource-button.png) button. This will take you to the 'Add data source' page. Complete the 'Add data source' form and click the ![Add](/images/add-button.png) button.

## Add data source form

![Data source form](/images/add-datasource-form.png)

### Name

The name that will used for your data source. The name is mandatory and must be unique. Choose a name that is descriptive enough as this will be what you will see when selecting a data source for a dashboard widget.

### Description

A longer description for the data source. This will be displayed in your data source list.

### Device

Select the device that you would like to source the data from.

### Type

Select the type of data source, either Raw or Statistical. You can read about the difference on the [quick start section](datasources/quickstart.md).

### Telemetry

If your device has logged data before, you can select one of the telemetry items from the list. If not, you can type the telemetry name, but note that it is case-sensitive.

### Data grouping

Statistical data source allow you to capture the time aggregation for your data. Please see the [quick start section](datasources/quickstart.md) for more information about available aggregations.

![Data grouping](/images/data-grouping.png)

## Testing the data source

To get a feel of how well your data source will perform on your dashboard you can hit the test button to do a sample query of the data. If the query is slow you should consider using a statistical data source type or up your data grouping so the data is aggregated. This will result in fewer data point but better query performance.

![Data source test](/images/data-source-test.png)
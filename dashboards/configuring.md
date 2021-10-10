# Configuring

![Dashboard layout](/images/dashboard-layout-named.png)

## Dashboard selector

The dashboard selector allows you to quickly switch between dashboards without having to go back to the dashboard list.

## Save

Dashboards changes aren't automatically saved. The save button allows you to save any changes you have made.

## Delete

Clicking the delete button will delete the dashboard you are currently viewing.

## Time series

Time series allows you to select a time range to fetch telemetry data for. By default the time series is set to today only. Clicking the button will pop out a time range selector for custom time range selection and some shortcuts to some popular time ranges.

![Time series](/images/time-series.png)

## Live

Clicking the live button will start data polling on your dashboard. The dashboard data will be refreshed every few seconds. Click the button again to pause the polling.

## Add widget

Clicking the add widget button will add a new blank widget to your dashboard. A widget will have a tile, initially set to "Undefined", a widget menu from where you can choose to "Edit", "Duplicate" and "Delete" a widget, and a resize handle which you can click and drag to change the size of the widget.

![Blank widget](/images/blank-widget-named.png)

## Configuring a widget

Select the "Edit" option from the Widget menu. This will open the widget configuration popout. Complete the widget configuration form and click the update button.

### Widget detail form

![Detail form](/images/detail-form.png)

#### Title

Title that will be displayed on your widget

#### Description

Description for you widget

### Widget visual form

![Detail form](/images/visual-form.png)

Select a visual to use for display. For more information on the visualization type, please see the [quick start guide](dashboards/quickstart.md).

### Widget data source form

![Data source form](/images/datasource-form.png)

#### Data source

The [data source](datasources/quickstart.md) used that you would like to visualize.

#### Statistic

The statistical value you would like to use as data points. For the location visual this will not be available as the "Location" telemetry key will be used as the data points.

#### Add another data source

This allows you to add another data source to be displayed. Some visualizations will display the multiple data set but others will ignore them when they aren't applicable.

### Single value options

![Single value options](/images/single-val-options.png)

#### No data

The text to display when there is not data to display

#### Green color

The color to display when the value is within the green range.

#### Red color

The color to display when the value is within the red range.

#### Red from

The value from which the red range starts.

#### Green from

The value from which the green range starts.

#### Color display

This controls if the widget background or the widget value changes color when it gets to the specified range.

### Guage options

![Guage options](/images/guage-options.png)

#### Minimum

The minimum value to show on the guage.

#### Maximum

The maximum value to show on the guage.

#### Green color

The color to use for the green range.

#### Green from

The value from which the green range starts.

#### Green to

The value from where the green range ends.

#### Yellow color

The color to use for the yellow range.

#### Yellow from

The value where the yellow range starts.

#### Yellow to

The value where the yellow range ends.

#### Red color

The color to use for the red range.

#### Red from

The value where the red range starts.

#### Red to

The value where the red range ends.

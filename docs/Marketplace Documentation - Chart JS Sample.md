# Chart JS Sample – Marketplace Documentation

Sample version 1.1.0 · Mendix Studio Pro 10.24.17 · Web (React client) · Complete app package

## Industry

All industries (cross-industry).

## Categories

- Sample apps / Demos
- Visualization / Charts

## Component tagline

Sample app for the Chart JS widgets: bar, line, area and pie charts on one page.

(80 characters)

## About

Chart JS Sample is a small Mendix app that shows the Chart JS widgets at work. One page, the Dashboard, holds seven charts: four bar charts (grouped, horizontal, stacked, stacked horizontal), an area chart, a line chart with two axes and a pie chart. Every chart has buttons to export and to zoom, shows a tooltip, and reacts to a click.

Use the sample to see how the widgets are configured before you add them to your own app: how a series gets its data from a microflow or from the database, how options are switched with Boolean attributes, and how a click on a chart reaches a microflow.

Version 1.1.0 is for Mendix Studio Pro 10.24.17. The functionality is the same as before. New in 1.1.0: the package contains the data snapshot with five sample rows, so the charts show data on the first run (the 1.0.0 package did not). The converted app was started on the 10.24.17 runtime and checked in a browser: all seven charts are drawn and the browser console shows no errors.

The package is a complete app, not a module. To add the charts to your own app, use the Chart JS widgets: https://github.com/bharathidas/ChartJS

Sample app on GitHub: https://github.com/bharathidas/ChartJSDemo

## Typical usage scenario

- Try the Chart JS widgets before you install them in your own app.
- Look up how a multi-series bar, line or area chart is fed from microflows.
- Look up how a pie chart is fed from the database.
- Copy the option pattern (one object with Boolean attributes for stacked, horizontal, values on top, export and zoom).
- Copy the click pattern (clicked label, value and series stored in an attribute, then a microflow).
- Start a dashboard from the four building blocks.

## Features and limitations

**Features**

- Dashboard page with seven charts: grouped, horizontal, stacked and stacked horizontal bars, area, multi-axis line, pie.
- Two data series from microflows (ACT_Series1, ACT_Series2); pie chart from the database.
- Options from attributes of one object (TestChart): stacked, horizontal, values on top, export button, zoom buttons, multi axis.
- Click on a bar, point or slice shows a message such as "Label=jan; Value=10; Dataset=Series 1;".
- Pages to view, add, change and delete the chart data (Chart_Overview, Chart_NewEdit).
- Building blocks ChartJSBar, ChartJSLine, ChartJSArea and ChartJSPie.
- Includes the widget packages Chart JS Bar, Line, Area, Pie and ChartJSTwo (1.0.0) and a data snapshot with five sample rows.

**Limitations**

- Complete app package; it cannot be imported as a module into an existing app.
- The value attribute is a String; enter numbers only.
- The two sample series have two rows each. More rows appear only in the pie chart.
- Series colors change on every page load, because no color attribute is set.
- App security is off in the sample.
- Web only; no native mobile profile.

## Dependencies

- Mendix Studio Pro 10.24.17 or a later 10.24 version.
- Nothing else. The package contains all modules and widgets it needs (Atlas Core, Atlas Web Content, Data Widgets, Administration, Nanoflow Commons, Web Actions, Feedback Module, File Uploader).

## Installation

1. Download `Chartjs2.mpk`.
2. In Studio Pro 10.24.17, choose File > Import app package and select the file.
3. Choose a folder for the new app and confirm.
4. Run the app locally (F5) and open it in the browser (F9).
5. Click View Dashboard on the home page.

Do not use Import module package; this is a complete app.

## Configuration

No configuration is needed to run the sample.

To change the data: open Item in the menu, add or change rows (a label and a numeric value), and open the Dashboard again.

To change the options: open the domain model of ChartJSModule and change the default values of the TestChart attributes (stacked, isHorizontal, ShowValueonTop, ShowExport, ShowZoom, EnableMultiAxis), then run the app again.

To reuse a chart in your own app: import ChartJSModule.mpk from https://github.com/bharathidas/ChartJS/releases, drag a building block onto a page inside a data view with your options object, and point the series at your own microflows or entities.

## Known bugs

- The model check shows 22 warnings. They come from Atlas page templates, building blocks, menu items without an action and a legacy drop-down, and do not stop the app.
- The series microflows retrieve without a sort order, so which rows form Series 1 and Series 2 depends on the database order.
- The ChartJSTwo widget package is included but is not placed on a page.

## FAQ

**Can I import this into my existing app?**
No. It is a complete app package. Import ChartJSModule.mpk from the Chart JS widgets repository into your app instead.

**Why are the charts empty?**
There are no Chart rows. Open Item in the menu and add rows. The bar, line and area charts need at least four rows for two series.

**Why do the colors change when I reload the page?**
No color attribute is selected in the sample, so the widgets choose the colors. Select a color attribute with hex values, for example #4dc9f6,#f67019, to fix them.

**How do I get the clicked value in a microflow?**
Select a String attribute for "on click value" and a microflow for "On click action". The attribute receives a text such as Label=jan; Value=10; Dataset=Series 1;.

**Do I need to log in?**
No. App security is off in the sample.

**Does it work in older Mendix versions?**
This version is for Studio Pro 10.24.17. The earlier package was made with Studio Pro 10.24.6.

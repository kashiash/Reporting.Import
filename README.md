# Overview
This repository contains a console application project designed to convert third party reports into files supported by DevExpress Reports (XML). You can use these output files to [Load Report Layouts](https://docs.devexpress.com/XtraReports/2666/detailed-guide-to-devexpress-reporting/store-and-distribute-reports/store-report-layouts-and-documents/load-report-layouts) within the DevExpress Visual Studio Report Designer, DevExpress End-User Report Designer or display the report at runtime.

# Project Specifics
You can modify the following options in project properties:
 *	The **Build** Tab’s **Conditional compilation symbols** specifies a list of all supported third-party suppliers (all are enabled by default);
 *	The **Debug** tab allows you to specify **Command line arguments**. These arguments determine input and output files ("in" and "out" parameters). If the file to be converted is stored within the application’s root folder, you only need to specify its name. Otherwise, specify a full path to the file. Similarly, for the "out" parameter, specify the name and path to the resulting file.

# Examples of use
You can launch the application either from Visual Studio, or from the command line (with both parameters defined).
Use the following command line to convert multiple reports simultaneously:
```
FOR /R Reports %R IN (*.rpt) DO ReportsImport "/in:%R" "/out:%R.repx"
```
The following command starts the conversion process for an individual report: 
```
C:\0>ReportsImport /in:c:\0\crystal\file.rpt /out:c:\0\converted\testreport.repx
```

# Limitations
This report conversion/import tool is limited in scope (due to differences between DevExpress Reports and other reporting tools). Please review the [requirements and limitations](https://docs.devexpress.com/XtraReports/1468/get-started-with-devexpress-reporting/add-a-report-to-your-.net-application/convert-third-party-reports-to-devexpress-reports) related to this product before converting your existing reports.

**_Note: This project intentionally does not contain third party libraries. To compile the application, you need to manually add references to required assemblies._**

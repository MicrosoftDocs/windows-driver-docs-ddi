---
UID: NA:winddiui
ms.assetid: 53a5312f-9f75-3637-bb7f-d79817f00a15
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Winddiui.h header



This header is used by print. For more information, see
- [print](../_print/index.md)

Winddiui.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [DevQueryPrintEx function](nf-winddiui-devqueryprintex.md) | A printer interface DLL's DevQueryPrintEx function determines if a specified print job is compatible with the printer's current configuration and can therefore be printed. |
| [DrvConvertDevMode function](nf-winddiui-drvconvertdevmode.md) | A printer interface DLL's DrvConvertDevMode function converts a printer's DEVMODEW structure from one version to another. |
| [DrvDeviceCapabilities function](nf-winddiui-drvdevicecapabilities.md) | A printer interface DLL's DrvDeviceCapabilities function returns requested information about a printer's capabilities. |
| [DrvDevicePropertySheets function](nf-winddiui-drvdevicepropertysheets.md) | A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties. |
| [DrvDocumentEvent function](nf-winddiui-drvdocumentevent.md) | A printer interface DLL's DrvDocumentEvent function can handle certain events associated with printing a document. |
| [DrvDocumentPropertySheets function](nf-winddiui-drvdocumentpropertysheets.md) | A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties. |
| [DrvDriverEvent function](nf-winddiui-drvdriverevent.md) | The print spooler calls a printer interface DLL's DrvDriverEvent function when the spooler processes driver-specific events that might require action by the printer driver. |
| [DrvPrinterEvent function](nf-winddiui-drvprinterevent.md) | A printer interface DLL's DrvPrinterEvent function is called by the print spooler when processing printer-specific events that might require action by the printer driver. |
| [DrvQueryColorProfile function](nf-winddiui-drvquerycolorprofile.md) | The DrvQueryColorProfile function allows a printer interface DLL to specify an ICC profile to use for color management. |
| [DrvQueryJobAttributes function](nf-winddiui-drvqueryjobattributes.md) | The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (&#0034;N-up&#0034; printing), printing multiple copies of each page, collating pages, and printing pages in reverse order. |
| [DrvSplAbort function](nf-winddiui-drvsplabort.md) | "." |
| [DrvSplClose function](nf-winddiui-drvsplclose.md) | "." |
| [DrvSplDeviceCaps function](nf-winddiui-drvspldevicecaps.md) | A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities. |
| [DrvSplEndDoc function](nf-winddiui-drvsplenddoc.md) | "." |
| [DrvSplEndPage function](nf-winddiui-drvsplendpage.md) | "." |
| [DrvSplStartDoc function](nf-winddiui-drvsplstartdoc.md) | "." |
| [DrvSplStartPage function](nf-winddiui-drvsplstartpage.md) | "." |
| [DrvSplWritePrinter function](nf-winddiui-drvsplwriteprinter.md) | "." |
| [DrvUpgradePrinter function](nf-winddiui-drvupgradeprinter.md) | A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_ATTRIBUTE_INFO_1 structure](ns-winddiui-_attribute_info_1.md) | The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_2 structure](ns-winddiui-_attribute_info_2.md) | The ATTRIBUTE_INFO_2 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_3 structure](ns-winddiui-_attribute_info_3.md) | The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_4 structure](ns-winddiui-_attribute_info_4.md) | The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. |
| [_DEVICEPROPERTYHEADER structure](ns-winddiui-_devicepropertyheader.md) | The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function. |
| [_DEVQUERYPRINT_INFO structure](ns-winddiui-_devqueryprint_info.md) | The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's DevQueryPrintEx function. |
| [_DOCEVENT_CREATEDCPRE structure](ns-winddiui-_docevent_createdcpre.md) | The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to DrvDocumentEvent and IPrintOemUI2 |
| [_DOCEVENT_ESCAPE structure](ns-winddiui-_docevent_escape.md) | The DOCEVENT_ESCAPE structure is a container for values used as parameters for the ExtEscape function. |
| [_DOCEVENT_FILTER structure](ns-winddiui-_docevent_filter.md) | The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See DrvDocumentEvent for a complete list of the document events. |
| [_DOCUMENTPROPERTYHEADER structure](ns-winddiui-_documentpropertyheader.md) | The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDocumentPropertySheets function. |
| [_DRIVER_UPGRADE_INFO_1 structure](ns-winddiui-_driver_upgrade_info_1.md) | The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
| [_DRIVER_UPGRADE_INFO_2 structure](ns-winddiui-_driver_upgrade_info_2.md) | The DRIVER_UPGRADE_INFO_2 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
| [_PRINTER_EVENT_ATTRIBUTES_INFO structure](ns-winddiui-_printer_event_attributes_info.md) | The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer. |

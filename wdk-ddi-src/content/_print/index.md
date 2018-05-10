---
UID: TP:print
ms.assetid: fc0e0b85-603b-35c9-9d94-fc5cb18ea7c1
ms.author: windowsdriverdev
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Print devices

## -description

Overview of the Print devices technology.

To develop Print devices, you need these headers:

 * [bidispl.h](..\bidispl\index.md)
 * [compstui.h](..\compstui\index.md)
 * [d4drvif.h](..\d4drvif\index.md)
 * [d4iface.h](..\d4iface\index.md)
 * [filterpipeline.h](..\filterpipeline\index.md)
 * [icm.h](..\icm\index.md)
 * [mxdc.h](..\mxdc\index.md)
 * [prcomoem.h](..\prcomoem\index.md)
 * [prdrvcom.h](..\prdrvcom\index.md)
 * [printerextension.h](..\printerextension\index.md)
 * [printoem.h](..\printoem\index.md)
 * [prnasntp.h](..\prnasntp\index.md)
 * [prntfont.h](..\prntfont\index.md)
 * [tcpxcv.h](..\tcpxcv\index.md)
 * [usbprint.h](..\usbprint\index.md)
 * [winddiui.h](..\winddiui\index.md)
 * [winppi.h](..\winppi\index.md)
 * [winsplp.h](..\winsplp\index.md)
 * [winspool.h](..\winspool\index.md)
 * [xpsrassvc.h](..\xpsrassvc\index.md)

For the programming guide, see [Print devices](https://docs.microsoft.com/en-us/windows-hardware/drivers/print).

## Functions

| Title   | Description   |
| ---- |:---- |
| [AddPortUI function](..\winsplp\nf-winsplp-addportui.md) | A port monitor UI DLL's AddPortUI function adds a printer port, then obtains port configuration information from the user and sends it to the port monitor server DLL. |
| [AddPrintDeviceObject function](..\winsplp\nf-winsplp-addprintdeviceobject.md) | The AddPrintDeviceObject print provider function creates a device object for a print provider queue. |
| [AppendPrinterNotifyInfoData function](..\winsplp\nf-winsplp-appendprinternotifyinfodata.md) | The print spooler's AppendPrinterNotifyInfoData function adds the contents of a specified PRINTER_NOTIFY_INFO_DATA structure to a specified PRINTER_NOTIFY_INFO structure. |
| [BindPrinter function](..\prdrvcom\nf-prdrvcom-bindprinter.md) | The IPrintOemPrintTicketProvider |
| [CallRouterFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-callrouterfindfirstprinterchangenotification.md) | "." |
| [ClosePort function](..\winsplp\nf-winsplp-closeport.md) | A language or port monitor's ClosePort function closes a printer port. |
| [ClosePrintProcessor function](..\winsplp\nf-winsplp-closeprintprocessor.md) | A print processor's ClosePrintProcessor function completes the printing of a print job and makes the associated handle invalid. |
| [CommonPropertySheetUIA function](..\compstui\nf-compstui-commonpropertysheetuia.md) | CPSUI's CommonPropertySheetUI function displays property sheet pages and allows user modifications to displayed values. |
| [CommonPropertySheetUIW function](..\compstui\nf-compstui-commonpropertysheetuiw.md) | CPSUI's CommonPropertySheetUI function displays property sheet pages and allows user modifications to displayed values. |
| [ConfigurePortUI function](..\winsplp\nf-winsplp-configureportui.md) | A port monitor UI DLL's ConfigurePortUI function obtains port configuration information from the user and sends it to the port monitor server DLL. |
| [ControlPrintProcessor function](..\winsplp\nf-winsplp-controlprintprocessor.md) | A print processor's ControlPrintProcessor function allows the spooler to control a print job. |
| [ConvertDevModeToPrintTicket function](..\prdrvcom\nf-prdrvcom-convertdevmodetoprintticket.md) | The IPrintOemPrintTicketProvider |
| [ConvertPrintTicketToDevMode function](..\prdrvcom\nf-prdrvcom-convertprinttickettodevmode.md) | The IPrintTicketProvider |
| [CreatePrinterIC function](..\winsplp\nf-winsplp-createprinteric.md) | "." |
| [DeleteJobNamedProperty function](..\winspool\nf-winspool-deletejobnamedproperty.md) | Deletes the named property for the specified print job on the specified printer. |
| [DeletePortUI function](..\winsplp\nf-winsplp-deleteportui.md) | A port monitor UI DLL's DeletePortUI function deletes a printer port. |
| [DeletePrinterIC function](..\winsplp\nf-winsplp-deleteprinteric.md) | "." |
| [DevQueryPrint function](..\winsplp\nf-winsplp-devqueryprint.md) | "." |
| [DevQueryPrintEx function](..\winddiui\nf-winddiui-devqueryprintex.md) | A printer interface DLL's DevQueryPrintEx function determines if a specified print job is compatible with the printer's current configuration and can therefore be printed. |
| [DrvConvertDevMode function](..\winddiui\nf-winddiui-drvconvertdevmode.md) | A printer interface DLL's DrvConvertDevMode function converts a printer's DEVMODEW structure from one version to another. |
| [DrvDeviceCapabilities function](..\winddiui\nf-winddiui-drvdevicecapabilities.md) | A printer interface DLL's DrvDeviceCapabilities function returns requested information about a printer's capabilities. |
| [DrvDevicePropertySheets function](..\winddiui\nf-winddiui-drvdevicepropertysheets.md) | A printer interface DLL's DrvDevicePropertySheets function is responsible for creating property sheet pages that describe a printer's properties. |
| [DrvDocumentEvent function](..\winddiui\nf-winddiui-drvdocumentevent.md) | A printer interface DLL's DrvDocumentEvent function can handle certain events associated with printing a document. |
| [DrvDocumentPropertySheets function](..\winddiui\nf-winddiui-drvdocumentpropertysheets.md) | A printer interface DLL's DrvDocumentPropertySheets function is responsible for creating property sheet pages that describe a print document's properties. |
| [DrvDriverEvent function](..\winddiui\nf-winddiui-drvdriverevent.md) | The print spooler calls a printer interface DLL's DrvDriverEvent function when the spooler processes driver-specific events that might require action by the printer driver. |
| [DrvPopulateFilterServices function](..\filterpipeline\nf-filterpipeline-drvpopulatefilterservices.md) | The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter. |
| [DrvPrinterEvent function](..\winddiui\nf-winddiui-drvprinterevent.md) | A printer interface DLL's DrvPrinterEvent function is called by the print spooler when processing printer-specific events that might require action by the printer driver. |
| [DrvQueryColorProfile function](..\winddiui\nf-winddiui-drvquerycolorprofile.md) | The DrvQueryColorProfile function allows a printer interface DLL to specify an ICC profile to use for color management. |
| [DrvQueryJobAttributes function](..\winddiui\nf-winddiui-drvqueryjobattributes.md) | The DrvQueryJobAttributes function allows a printer interface DLL to specify support for such capabilities as printing multiple document pages on a physical page (&#0034;N-up&#0034; printing), printing multiple copies of each page, collating pages, and printing pages in reverse order. |
| [DrvSplAbort function](..\winddiui\nf-winddiui-drvsplabort.md) | "." |
| [DrvSplClose function](..\winddiui\nf-winddiui-drvsplclose.md) | "." |
| [DrvSplDeviceCaps function](..\winddiui\nf-winddiui-drvspldevicecaps.md) | A printer interface DLL's DrvSplDeviceCaps function queries a printer for its capabilities. |
| [DrvSplEndDoc function](..\winddiui\nf-winddiui-drvsplenddoc.md) | "." |
| [DrvSplEndPage function](..\winddiui\nf-winddiui-drvsplendpage.md) | "." |
| [DrvSplStartDoc function](..\winddiui\nf-winddiui-drvsplstartdoc.md) | "." |
| [DrvSplStartPage function](..\winddiui\nf-winddiui-drvsplstartpage.md) | "." |
| [DrvSplWritePrinter function](..\winddiui\nf-winddiui-drvsplwriteprinter.md) | "." |
| [DrvUpgradePrinter function](..\winddiui\nf-winddiui-drvupgradeprinter.md) | A printer interface DLL's DrvUpgradePrinter function is used for updating a printer's registry settings when a new version of the driver is added to a system. |
| [EnumJobNamedProperties function](..\winspool\nf-winspool-enumjobnamedproperties.md) | "." |
| [EnumPrintProcessorDatatypesA function](..\winspool\nf-winspool-enumprintprocessordatatypesa.md) | A print processor's EnumPrintProcessorDatatypes function enumerates the data types that the print processor supports. |
| [ExtDeviceMode function](..\winspool\nf-winspool-extdevicemode.md) | The ExtDeviceMode function is provided only for compatibility with 16-bit applications. |
| [FindFirstPrinterChangeNotification function](..\winspool\nf-winspool-findfirstprinterchangenotification.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [FreePrintNamedPropertyArray function](..\winspool\nf-winspool-freeprintnamedpropertyarray.md) | "." |
| [FreePrintPropertyValue function](..\winspool\nf-winspool-freeprintpropertyvalue.md) | Frees the value that is retrieved using GetJobNamedPropertyValue function. |
| [GdiDeleteSpoolFileHandle function](..\winppi\nf-winppi-gdideletespoolfilehandle.md) | The GdiDeleteSpoolFileHandle function releases a spool file handle. |
| [GdiEndDocEMF function](..\winppi\nf-winppi-gdienddocemf.md) | The GdiEndDocEMF function ends EMF playback operations for an EMF-formatted print job. |
| [GdiEndPageEMF function](..\winppi\nf-winppi-gdiendpageemf.md) | The GdiEndPageEMF function ends EMF playback operations for a physical page of an EMF-formatted print job. |
| [GdiGetDC function](..\winppi\nf-winppi-gdigetdc.md) | The GdiGetDC function returns a handle to a printer's device context. |
| [GdiGetDevmodeForPage function](..\winppi\nf-winppi-gdigetdevmodeforpage.md) | The GdiGetDevmodeForPage function returns DEVMODEW structures for the specified and previous pages of a print job. |
| [GdiGetPageCount function](..\winppi\nf-winppi-gdigetpagecount.md) | The GdiGetPageCount function returns the number of pages in a print job. |
| [GdiGetPageHandle function](..\winppi\nf-winppi-gdigetpagehandle.md) | The GdiGetPageHandle function returns a handle to the specified page within a print job. |
| [GdiGetSpoolFileHandle function](..\winppi\nf-winppi-gdigetspoolfilehandle.md) | The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file. |
| [GdiPlayPageEMF function](..\winppi\nf-winppi-gdiplaypageemf.md) | The GdiPlayPageEMF function plays the EMF records within a specified rectangle for one document page of a spooled print job. |
| [GdiResetDCEMF function](..\winppi\nf-winppi-gdiresetdcemf.md) | The GdiResetDCEMF function resets a printer's device context during playback of a spooled EMF print job. |
| [GdiStartDocEMF function](..\winppi\nf-winppi-gdistartdocemf.md) | The GdiStartDocEMF function performs initialization operations for an EMF-formatted print job. |
| [GdiStartPageEMF function](..\winppi\nf-winppi-gdistartpageemf.md) | The GdiStartPageEMF function performs initialization operations for a physical page of an EMF-formatted print job. |
| [GenerateCopyFilePaths function](..\winsplp\nf-winsplp-generatecopyfilepaths.md) | A Point and Print DLL's GenerateCopyFilePaths function is used for modifying the source and destination paths used by print spoolers when they copy print queue-associated files to a print client. |
| [GetCPSUIUserData function](..\compstui\nf-compstui-getcpsuiuserdata.md) | CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function. |
| [GetJobAttributes function](..\winsplp\nf-winsplp-getjobattributes.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [GetJobAttributesEx function](..\winsplp\nf-winsplp-getjobattributesex.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [GetJobNamedPropertyValue function](..\winspool\nf-winspool-getjobnamedpropertyvalue.md) | Retrieves the value of the named property for the specified print job on the specified printer. |
| [GetPrintCapabilities function](..\prdrvcom\nf-prdrvcom-getprintcapabilities.md) | The IPrintTicketProvider |
| [GetPrintOutputInfo function](..\winspool\nf-winspool-getprintoutputinfo.md) | "." |
| [GetPrintProcessorCapabilities function](..\winsplp\nf-winsplp-getprintprocessorcapabilities.md) | A print processor's GetPrintProcessorCapabilities function returns capabilities associated with a specified input data type. |
| [GetSupportedVersions function](..\prdrvcom\nf-prdrvcom-getsupportedversions.md) | The IPrintTicketProvider |
| [ImpersonatePrinterClient function](..\winsplp\nf-winsplp-impersonateprinterclient.md) | ImpersonatePrinterClient resumes impersonation of the client, completing the operation begun by RevertToPrinterSelf. |
| [InitializeMonitor function](..\winsplp\nf-winsplp-initializemonitor.md) | "." |
| [InitializeMonitorEx function](..\winsplp\nf-winsplp-initializemonitorex.md) | "." |
| [InitializePrintMonitor function](..\winsplp\nf-winsplp-initializeprintmonitor.md) | The InitializePrintMonitor function is obsolete and is supported only for compatibility purposes. |
| [InitializePrintMonitor2 function](..\winsplp\nf-winsplp-initializeprintmonitor2.md) | A print monitor's InitializePrintMonitor2 function initializes a print monitor for use with clustered print servers. |
| [InitializePrintMonitorUI function](..\winsplp\nf-winsplp-initializeprintmonitorui.md) | A port monitor UI DLL's InitializePrintMonitorUI function supplies the print spooler with addresses of DLL functions. |
| [InitializePrintProvidor function](..\winsplp\nf-winsplp-initializeprintprovidor.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [IsValidDevmodeA function](..\winspool\nf-winspool-isvaliddevmodea.md) | The print spooler's IsValidDevmode function verifies that the contents of a DEVMODE structure are valid. |
| [IsValidDevmodeW function](..\winspool\nf-winspool-isvaliddevmodew.md) | The print spooler's IsValidDevmode function verifies that the contents of a DEVMODE structure are valid. |
| [LogJobInfoForBranchOffice function](..\winsplp\nf-winsplp-logjobinfoforbranchoffice.md) | Allows Branch Office clients to send job events to the host print server. |
| [MxdcGetPDEVAdjustment function](..\mxdc\nf-mxdc-mxdcgetpdevadjustment.md) | The MxdcGetPDEVAdjustment function is exported by a printer interface DLL and supplies printer configuration data for the Microsoft XPS Document Converter (MXDC). |
| [OEMAlphaBlend function](..\printoem\nf-printoem-oemalphablend.md) | OEMAlphaBlend function |
| [OEMBitBlt function](..\printoem\nf-printoem-oembitblt.md) | The OEMBitBlt function provides general bit-block transfer capabilities between device-managed surfaces, between GDI-managed standard-format bitmaps, or between a device-managed surface and a GDI-managed standard-format bitmap. |
| [OEMCommand function](..\printoem\nf-printoem-oemcommand.md) | OEMCommand function |
| [OEMCommandCallback function](..\printoem\nf-printoem-oemcommandcallback.md) | OEMCommandCallback function |
| [OEMCommonUIProp function](..\printoem\nf-printoem-oemcommonuiprop.md) | OEMCommonUIProp function |
| [OEMCompression function](..\printoem\nf-printoem-oemcompression.md) | OEMCompression function |
| [OEMCopyBits function](..\printoem\nf-printoem-oemcopybits.md) | The OEMCopyBits function performs translations between device-managed raster surfaces and GDI standard-format bitmaps. |
| [OEMDevMode function](..\printoem\nf-printoem-oemdevmode.md) | OEMDevMode function |
| [OEMDevQueryPrintEx function](..\printoem\nf-printoem-oemdevqueryprintex.md) | OEMDevQueryPrintEx function |
| [OEMDeviceCapabilities function](..\printoem\nf-printoem-oemdevicecapabilities.md) | OEMDeviceCapabilities function |
| [OEMDevicePropertySheets function](..\printoem\nf-printoem-oemdevicepropertysheets.md) | OEMDevicePropertySheets function |
| [OEMDisableDriver function](..\printoem\nf-printoem-oemdisabledriver.md) | OEMDisableDriver function |
| [OEMDisablePDEV function](..\printoem\nf-printoem-oemdisablepdev.md) | OEMDisablePDEV function |
| [OEMDitherColor function](..\printoem\nf-printoem-oemdithercolor.md) | The OEMDitherColor function requests the device to create a brush dithered against a device palette. |
| [OEMDocumentPropertySheets function](..\printoem\nf-printoem-oemdocumentpropertysheets.md) | OEMDocumentPropertySheets function |
| [OEMDownloadCharGlyph function](..\printoem\nf-printoem-oemdownloadcharglyph.md) | OEMDownloadCharGlyph function |
| [OEMDownloadFontHeader function](..\printoem\nf-printoem-oemdownloadfontheader.md) | OEMDownloadFontHeader function |
| [OEMDriverDMS function](..\printoem\nf-printoem-oemdriverdms.md) | OEMDriverDMS function |
| [OEMEnableDriver function](..\printoem\nf-printoem-oemenabledriver.md) | OEMEnableDriver function |
| [OEMEnablePDEV function](..\printoem\nf-printoem-oemenablepdev.md) | OEMEnablePDEV function |
| [OEMEndDoc function](..\printoem\nf-printoem-oemenddoc.md) | The OEMEndDoc function is called by the GDI when it has finished sending a document to the driver for rendering. |
| [OEMEscape function](..\printoem\nf-printoem-oemescape.md) | The OEMEscape function retrieves information from a device that is not available in a device-independent device driver interface; the particular query depends on the value of the iEsc parameter. |
| [OEMFillPath function](..\printoem\nf-printoem-oemfillpath.md) | The OEMFillPath function handles the filling of closed paths. |
| [OEMFilterGraphics function](..\printoem\nf-printoem-oemfiltergraphics.md) | OEMFilterGraphics function |
| [OEMFontInstallerDlgProc function](..\printoem\nf-printoem-oemfontinstallerdlgproc.md) | OEMFontInstallerDlgProc function |
| [OEMFontManagement function](..\printoem\nf-printoem-oemfontmanagement.md) | The OEMFontManagement function is an optional entry point provided for PostScript devices. |
| [OEMGetGlyphMode function](..\printoem\nf-printoem-oemgetglyphmode.md) | The OEMGetGlyphMode function informs the GDI how to cache glyph information. |
| [OEMGetInfo function](..\printoem\nf-printoem-oemgetinfo.md) | OEMGetInfo function |
| [OEMGradientFill function](..\printoem\nf-printoem-oemgradientfill.md) | The OEMGradientFill function shades the specified primitives. |
| [OEMHalftonePattern function](..\printoem\nf-printoem-oemhalftonepattern.md) | OEMHalftonePattern function |
| [OEMIcmCreateColorTransform function](..\printoem\nf-printoem-oemicmcreatecolortransform.md) | The OEMIcmCreateColorTransform function creates an ICM color transform. |
| [OEMIcmDeleteColorTransform function](..\printoem\nf-printoem-oemicmdeletecolortransform.md) | The OEMIcmDeleteColorTransform function deletes the specified color transform. |
| [OEMImageProcessing function](..\printoem\nf-printoem-oemimageprocessing.md) | OEMImageProcessing function |
| [OEMLineTo function](..\printoem\nf-printoem-oemlineto.md) | The OEMLineTo function draws a single, solid, integer-only cosmetic line. |
| [OEMMemoryUsage function](..\printoem\nf-printoem-oemmemoryusage.md) | This function is obsolete for Windows XP and later.wcs |
| [OEMNextBand function](..\printoem\nf-printoem-oemnextband.md) | The OEMNextBand function is called by GDI when it has finished drawing a band for a physical page, so that the driver can send the band to the printer. |
| [OEMOutputCharStr function](..\printoem\nf-printoem-oemoutputcharstr.md) | OEMOutputCharStr function |
| [OEMPDriverEvent function](..\printoem\nf-printoem-oempdriverevent.md) | OEMPDriverEvent function |
| [OEMPaint function](..\printoem\nf-printoem-oempaint.md) | The OEMPaint function is obsolete, and is no longer called by GDI in Windows 2000 and later. See DrvPaint. |
| [OEMPlgBlt function](..\printoem\nf-printoem-oemplgblt.md) | The OEMPlgBlt function provides rotate bit-block transfer capabilities between combinations of device-managed and GDI-managed surfaces. |
| [OEMPrinterEvent function](..\printoem\nf-printoem-oemprinterevent.md) | OEMPrinterEvent function |
| [OEMQueryAdvanceWidths function](..\printoem\nf-printoem-oemqueryadvancewidths.md) | The OEMQueryAdvanceWidths function returns character advance widths for a specified set of glyphs. |
| [OEMQueryColorProfile function](..\printoem\nf-printoem-oemquerycolorprofile.md) | OEMQueryColorProfile function |
| [OEMQueryDeviceSupport function](..\printoem\nf-printoem-oemquerydevicesupport.md) | The OEMQueryDeviceSupport function returns requested device-specific information. |
| [OEMQueryFont function](..\printoem\nf-printoem-oemqueryfont.md) | The OEMQueryFont function is used by GDI to get the IFIMETRICS structure for a given font. |
| [OEMQueryFontData function](..\printoem\nf-printoem-oemqueryfontdata.md) | The OEMQueryFontData function retrieves information about a realized font. |
| [OEMQueryFontTree function](..\printoem\nf-printoem-oemqueryfonttree.md) | The OEMQueryFontTree function provides GDI with a pointer to a structure that defines one of the following |
| [OEMRealizeBrush function](..\printoem\nf-printoem-oemrealizebrush.md) | The OEMRealizeBrush function requests that the driver realize a specified brush for a specified surface. |
| [OEMResetPDEV function](..\printoem\nf-printoem-oemresetpdev.md) | OEMResetPDEV function |
| [OEMSendFontCmd function](..\printoem\nf-printoem-oemsendfontcmd.md) | OEMSendFontCmd function |
| [OEMSendPage function](..\printoem\nf-printoem-oemsendpage.md) | The OEMSendPage function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer. |
| [OEMStartBanding function](..\printoem\nf-printoem-oemstartbanding.md) | The OEMStartBanding function is called by GDI when it is ready to start sending bands of a physical page to the driver for rendering. |
| [OEMStartDoc function](..\printoem\nf-printoem-oemstartdoc.md) | The OEMStartDoc function is called by GDI when it is ready to start sending a document to the driver for rendering. |
| [OEMStartPage function](..\printoem\nf-printoem-oemstartpage.md) | The OEMStartPage function is called by GDI when it is ready to start sending the contents of a physical page to the driver for rendering. |
| [OEMStretchBlt function](..\printoem\nf-printoem-oemstretchblt.md) | The OEMStretchBlt function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces. |
| [OEMStretchBltROP function](..\printoem\nf-printoem-oemstretchbltrop.md) | The OEMStretchBltROP function performs a stretching bit-block transfer using a raster operation (ROP). |
| [OEMStrokeAndFillPath function](..\printoem\nf-printoem-oemstrokeandfillpath.md) | The OEMStrokeAndFillPath function concurrently strokes and fills a path. |
| [OEMStrokePath function](..\printoem\nf-printoem-oemstrokepath.md) | The OEMStrokePath function strokes a path. |
| [OEMTTDownloadMethod function](..\printoem\nf-printoem-oemttdownloadmethod.md) | OEMTTDownloadMethod function |
| [OEMTTYGetInfo function](..\printoem\nf-printoem-oemttygetinfo.md) | OEMTTYGetInfo function |
| [OEMTextOut function](..\printoem\nf-printoem-oemtextout.md) | The OEMTextOut function calls for the driver to render a set of glyphs at specified positions. |
| [OEMTextOutAsBitmap function](..\printoem\nf-printoem-oemtextoutasbitmap.md) | OEMTextOutAsBitmap function |
| [OEMTransparentBlt function](..\printoem\nf-printoem-oemtransparentblt.md) | The OEMTransparentBlt function provides bit-block transfer capabilities with transparency. |
| [OEMUpdateExternalFonts function](..\printoem\nf-printoem-oemupdateexternalfonts.md) | OEMUpdateExternalFonts function |
| [OEMUpgradePrinter function](..\printoem\nf-printoem-oemupgradeprinter.md) | OEMUpgradePrinter function |
| [OEMUpgradeRegistry function](..\printoem\nf-printoem-oemupgraderegistry.md) | OEMUpgradeRegistry function |
| [OpenPort function](..\winsplp\nf-winsplp-openport.md) | A port monitor's OpenPort function opens a printer port. |
| [OpenPrintProcessor function](..\winsplp\nf-winsplp-openprintprocessor.md) | A print processor's OpenPrintProcessor function prepares the print processor for printing a job and returns a handle. |
| [PartialReplyPrinterChangeNotification function](..\winsplp\nf-winsplp-partialreplyprinterchangenotification.md) | The print spooler's PartialReplyPrinterChangeNotification function allows a print provider to update the spooler's database of printer changes associated with a notification handle. |
| [PlayGdiScriptOnPrinterIC function](..\winsplp\nf-winsplp-playgdiscriptonprinteric.md) | "." |
| [PrintDocumentOnPrintProcessor function](..\winsplp\nf-winsplp-printdocumentonprintprocessor.md) | A print processor's PrintDocumentOnPrintProcessor function converts a print job from a spooled format into raw data that can be sent to a print monitor. |
| [PrinterMessageBoxA function](..\winspool\nf-winspool-printermessageboxa.md) | "." |
| [PrinterMessageBoxW function](..\winspool\nf-winspool-printermessageboxw.md) | "." |
| [ProvidorFindClosePrinterChangeNotification function](..\winsplp\nf-winsplp-providorfindcloseprinterchangenotification.md) | "." |
| [ProvidorFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-providorfindfirstprinterchangenotification.md) | "." |
| [QueryDeviceNamespace function](..\prdrvcom\nf-prdrvcom-querydevicenamespace.md) | The IPrintTicketProvider |
| [ReadPort function](..\winsplp\nf-winsplp-readport.md) | A port monitor's ReadPort function reads data from a printer port. |
| [RemovePrintDeviceObject function](..\winsplp\nf-winsplp-removeprintdeviceobject.md) | The RemovePrintDeviceObject function removes a device object from a print provider queue. |
| [ReplyPrinterChangeNotification function](..\winsplp\nf-winsplp-replyprinterchangenotification.md) | The print spooler's ReplyPrinterChangeNotification function allows a print provider to update the spooler's database of print queue events associated with a notification handle, and to notify the client that print queue events have occurred. |
| [ReplyPrinterChangeNotificationEx function](..\winsplp\nf-winsplp-replyprinterchangenotificationex.md) | "." |
| [RevertToPrinterSelf function](..\winsplp\nf-winsplp-reverttoprinterself.md) | When RevertToPrinterSelf is called on an impersonating thread, it returns the token for the thread that is being impersonated. |
| [RouterAllocBidiMem function](..\winsplp\nf-winsplp-routerallocbidimem.md) | RouterAllocBidiMem allocates a block of memory of a specified size. This function is used by the port monitor to allocate memory for strings and binary objects. |
| [RouterAllocBidiResponseContainer function](..\winsplp\nf-winsplp-routerallocbidiresponsecontainer.md) | RouterAllocBidiResponseContainer allocates a BIDI_RESPONSE_CONTAINER structure containing a list of bidi responses. The bidi response list is an array of BIDI_RESPONSE_DATA structures. |
| [RouterAllocPrinterNotifyInfo function](..\winsplp\nf-winsplp-routerallocprinternotifyinfo.md) | The print spooler's RouterAllocPrinterNotifyInfo function allocates a PRINTER_NOTIFY_INFO structure and an array of PRINTER_NOTIFY_INFO_DATA structures. |
| [RouterCreatePrintAsyncNotificationChannel function](..\prnasntp\nf-prnasntp-routercreateprintasyncnotificationchannel.md) | The RouterCreatePrintAsyncNotificationChannel function creates an asynchronous notification channel that is associated with a printer or print server. |
| [RouterFreeBidiMem function](..\winsplp\nf-winsplp-routerfreebidimem.md) | RouterFreeBidiMem frees a block of memory that was previously allocated by RouterAllocBidiMem. |
| [RouterFreeBidiResponseContainer function](..\winsplp\nf-winsplp-routerfreebidiresponsecontainer.md) | RouterFreeBidiResponseContainer frees a BIDI_RESPONSE_CONTAINER structure previously allocated by RouterAllocBidiResponseContainer. |
| [RouterFreePrinterNotifyInfo function](..\winsplp\nf-winsplp-routerfreeprinternotifyinfo.md) | The print spooler's RouterFreePrinterNotifyInfo function deallocates a specified PRINTER_NOTIFY_INFO structure and its associated PRINTER_NOTIFY_INFO_DATA structure array. |
| [RouterGetPrintClassObject function](..\prnasntp\nf-prnasntp-routergetprintclassobject.md) | The RouterGetPrintClassObject function enumerates the list of print providers, searching for the print provider with the specified name and interface ID. |
| [RouterRegisterForPrintAsyncNotifications function](..\prnasntp\nf-prnasntp-routerregisterforprintasyncnotifications.md) | The RouterRegisterForPrintAsyncNotifications function registers for asynchronous notifications associated with a printer or print server. |
| [RouterUnregisterForPrintAsyncNotifications function](..\prnasntp\nf-prnasntp-routerunregisterforprintasyncnotifications.md) | The RouterUnregisterForPrintAsyncNotifications function unregisters for receiving asynchronous notifications associated with a printer or print server. |
| [SetCPSUIUserData function](..\compstui\nf-compstui-setcpsuiuserdata.md) | CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box. |
| [SetJobNamedProperty function](..\winspool\nf-winspool-setjobnamedproperty.md) | "." |
| [SplDeleteSpoolerPortEnd function](..\winsplp\nf-winsplp-spldeletespoolerportend.md) | "." |
| [SplDeleteSpoolerPortStart function](..\winsplp\nf-winsplp-spldeletespoolerportstart.md) | "." |
| [SplIsSessionZero function](..\winsplp\nf-winsplp-splissessionzero.md) | The SplIsSessionZero function determines whether a certain print job (print handle plus job ID) was issued in session zero. |
| [SplPromptUIInUsersSession function](..\winsplp\nf-winsplp-splpromptuiinuserssession.md) | The SplPromptUIInUsersSession function displays a standard message box in the session indicated by the printer handle and job ID. |
| [SpoolerCopyFileEvent function](..\winsplp\nf-winsplp-spoolercopyfileevent.md) | A Point and Print DLL's SpoolerCopyFileEvent function receives notifications of events associated with copying print queue-associated files to a print client, when the client connects to a print server. |
| [SpoolerFindClosePrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindcloseprinterchangenotification.md) | "." |
| [SpoolerFindFirstPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindfirstprinterchangenotification.md) | "." |
| [SpoolerFindNextPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerfindnextprinterchangenotification.md) | "." |
| [SpoolerFreePrinterNotifyInfo function](..\winsplp\nf-winsplp-spoolerfreeprinternotifyinfo.md) | "." |
| [SpoolerRefreshPrinterChangeNotification function](..\winsplp\nf-winsplp-spoolerrefreshprinterchangenotification.md) | "." |
| [UpdatePrintDeviceObject function](..\winsplp\nf-winsplp-updateprintdeviceobject.md) | The UpdatePrintDeviceObject function updates the properties of a device object that is in the print provider queue. |
| [ValidatePrintTicket function](..\prdrvcom\nf-prdrvcom-validateprintticket.md) | The IPrintOemPrintTicketProvider |
| [WaitForPrinterChange function](..\winspool\nf-winspool-waitforprinterchange.md) | "." |
| [WcsAssociateColorProfileWithDevice function](..\icm\nf-icm-wcsassociatecolorprofilewithdevice.md) | The WcsAssociateColorProfileWithDevice function associates a specified WCS color profile with a specified device. |
| [WcsCheckColors function](..\icm\nf-icm-wcscheckcolors.md) | The WcsCheckColors function determines whether the colors in an array lie within the output gamut of a specified WCS color transform. |
| [WcsCreateIccProfile function](..\icm\nf-icm-wcscreateiccprofile.md) | The WcsCreateIccProfile function converts a WCS profile into an ICC profile. |
| [WcsDisassociateColorProfileFromDevice function](..\icm\nf-icm-wcsdisassociatecolorprofilefromdevice.md) | The WcsDisassociateColorProfileFromDevice function disassociates a specified WCS color profile from a specified device. |
| [WcsEnumColorProfiles function](..\icm\nf-icm-wcsenumcolorprofiles.md) | The WcsEnumColorProfiles function enumerates all color profiles that satisfy the enumeration criteria in the specified profile management scope. |
| [WcsEnumColorProfilesSize function](..\icm\nf-icm-wcsenumcolorprofilessize.md) | The WcsEnumColorProfilesSize function returns the size, in bytes, of the buffer required by the WcsEnumColorProfiles function to enumerate color profiles. |
| [WcsGetDefaultColorProfile function](..\icm\nf-icm-wcsgetdefaultcolorprofile.md) | The WcsGetDefaultColorProfile function retrieves the default color profile for a device, or the device-independent default if the device is not specified. |
| [WcsGetDefaultColorProfileSize function](..\icm\nf-icm-wcsgetdefaultcolorprofilesize.md) | The WcsGetDefaultColorProfileSize function returns the size, in bytes, of the default color profile name for a device, including the NULL terminator. |
| [WcsGetUsePerUserProfiles function](..\icm\nf-icm-wcsgetuseperuserprofiles.md) | The WcsGetUsePerUserProfiles function determines whether the user has chosen to use a per-user profile association list for the specified device. |
| [WcsOpenColorProfileA function](..\icm\nf-icm-wcsopencolorprofilea.md) | The WcsOpenColorProfile function creates a handle to a specified color profile. |
| [WcsOpenColorProfileW function](..\icm\nf-icm-wcsopencolorprofilew.md) | The WcsOpenColorProfile function creates a handle to a specified color profile. |
| [WcsSetDefaultColorProfile function](..\icm\nf-icm-wcssetdefaultcolorprofile.md) | The WcsSetDefaultColorProfile function sets the default color profile name of the specified profile type in the specified profile management scope. |
| [WcsSetUsePerUserProfiles function](..\icm\nf-icm-wcssetuseperuserprofiles.md) | The WcsSetUsePerUserProfiles function allows the user to specify whether or not to use a per-user profile association list for the specified device. |
| [WcsTranslateColors function](..\icm\nf-icm-wcstranslatecolors.md) | The WcsTranslateColors function translates an array of colors from the source color space to the destination color space as defined by a color transform. |
| [WritePort function](..\winsplp\nf-winsplp-writeport.md) | A port monitor's WritePort function writes data to a printer port. |
| [XcvClosePort function](..\winsplp\nf-winsplp-xcvcloseport.md) | A port monitor server DLL's XcvClosePort function closes a printer port that was opened by XcvOpenPort. |
| [XcvDataPort function](..\winsplp\nf-winsplp-xcvdataport.md) | A port monitor server DLL's XcvDataPort function receives information from, and returns information to, the port monitor's UI DLL. |
| [XcvOpenPort function](..\winsplp\nf-winsplp-xcvopenport.md) | A port monitor server DLL's XcvOpenPort function opens a port for configuration operations. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [OEMCUIPCALLBACK callback function](..\printoem\nc-printoem-oemcuipcallback.md) | The OEMCUIPCALLBACK function type is used for defining callback functions that are specified by a user interface plug-in's IPrintOemUI |
| [PFNCOMPROPSHEET callback function](..\compstui\nc-compstui-pfncompropsheet.md) | The ComPropSheet function is supplied by CPSUI and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages. |
| [PFNGETINFO callback function](..\printoem\nc-printoem-pfngetinfo.md) | The UNIFONTOBJ_GetInfo callback function is provided by the Unidrv driver so that rendering plug-ins can obtain font or glyph information. |
| [PFNPROPSHEETUI callback function](..\compstui\nc-compstui-pfnpropsheetui.md) | The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation. |
| [PFN_DrvGetDriverSetting callback function](..\printoem\nc-printoem-pfn_drvgetdriversetting.md) | The DrvGetDriverSetting function is obsolete. |
| [PFN_DrvGetStandardVariable callback function](..\printoem\nc-printoem-pfn_drvgetstandardvariable.md) | This DrvGetStandardVariable function is obsolete. |
| [PFN_DrvUnidriverTextOut callback function](..\printoem\nc-printoem-pfn_drvunidrivertextout.md) | The DrvUnidriverTextOut function is obsolete. |
| [PFN_DrvUpdateUISetting callback function](..\printoem\nc-printoem-pfn_drvupdateuisetting.md) | The DrvUpdateUISetting function is obsolete. |
| [PFN_DrvUpgradeRegistrySetting callback function](..\printoem\nc-printoem-pfn_drvupgraderegistrysetting.md) | The DrvUpgradeRegistrySetting function is obsolete. |
| [PFN_DrvWriteAbortBuf callback function](..\printoem\nc-printoem-pfn_drvwriteabortbuf.md) | The DrvWriteAbortBuf function is obsolete. |
| [PFN_DrvWriteSpoolBuf callback function](..\printoem\nc-printoem-pfn_drvwritespoolbuf.md) | The DrvWriteSpoolBuf function pointed to by this function pointer is obsolete. |
| [PFN_DrvXMoveTo callback function](..\printoem\nc-printoem-pfn_drvxmoveto.md) | The DrvXMoveTo function is obsolete. |
| [PFN_DrvYMoveTo callback function](..\printoem\nc-printoem-pfn_drvymoveto.md) | The DrvYMoveTo function is obsolete. |
| [ROUTER_NOTIFY_CALLBACK callback function](..\winsplp\nc-winsplp-router_notify_callback.md) | "." |
| [_CPSUICALLBACK callback function](..\compstui\nc-compstui-_cpsuicallback.md) | The _CPSUICALLBACK function type is used by CPSUI applications (including printer interface DLLs) for defining a callback function intended for use as a CPSUI message handler. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [BranchOfficeJobData structure](..\winsplp\ns-winsplp-branchofficejobdata.md) | This structure contains the type of event to log (eEventType), the job ID, and the data required by the event. |
| [BranchOfficeJobDataContainer structure](..\winsplp\ns-winsplp-branchofficejobdatacontainer.md) | This structure defines a container for one or more BranchOfficeJobData structures to sent to a server. |
| [BranchOfficeJobDataError structure](..\winsplp\ns-winsplp-branchofficejobdataerror.md) | This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler. |
| [BranchOfficeJobDataPipelineFailed structure](..\winsplp\ns-winsplp-branchofficejobdatapipelinefailed.md) | Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler. |
| [BranchOfficeJobDataPrinted structure](..\winsplp\ns-winsplp-branchofficejobdataprinted.md) | Contains the necessary data for logging a branch office job completed event on a remote server. This is based on standard job-related data available to the spooler. |
| [BranchOfficeJobDataRendered structure](..\winsplp\ns-winsplp-branchofficejobdatarendered.md) | Contains the necessary data for logging a branch office job Pipeline Rendering Event on a remote server. This is based on job-related data available to the spooler. |
| [BranchOfficeLogOfflineFileFull structure](..\winsplp\ns-winsplp-branchofficelogofflinefilefull.md) | Contains the necessary data for logging that the offline log archive on the current client overflowed at some point. |
| [IPPARAMS structure](..\printoem\ns-printoem-ipparams.md) | The IPPARAMS structure is used as an input parameter to a rendering plug-in's IPrintOemUni |
| [MESSAGEBOX_PARAMS structure](..\winsplp\ns-winsplp-messagebox_params.md) | The MESSAGEBOX_PARAMS structure is used by the SplPromptUIInUsersSession function to hold information about the appearance and behavior of a message box. |
| [OEMMEMORYUSAGE structure](..\printoem\ns-printoem-oemmemoryusage.md) | The OEMMEMORYUSAGE structure is used as an input parameter to a rendering plug-in's IPrintOemUni |
| [PrintNamedProperty structure](..\winspool\ns-winspool-printnamedproperty.md) | "." |
| [PrintPropertiesCollection structure](..\winspool\ns-winspool-printpropertiescollection.md) | "." |
| [PrintPropertyValue structure](..\winspool\ns-winspool-printpropertyvalue.md) | "." |
| [SHOWUIPARAMS structure](..\winsplp\ns-winsplp-showuiparams.md) | The SplPromptUIInUsersSession function uses the SHOWUIPARAMS structure to hold information about the appearance and behavior of a message box. |
| [_ATTRIBUTE_INFO_1 structure](..\winddiui\ns-winddiui-_attribute_info_1.md) | The ATTRIBUTE_INFO_1 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_2 structure](..\winddiui\ns-winddiui-_attribute_info_2.md) | The ATTRIBUTE_INFO_2 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_3 structure](..\winddiui\ns-winddiui-_attribute_info_3.md) | The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_3 structure](..\winsplp\ns-winsplp-_attribute_info_3.md) | The ATTRIBUTE_INFO_3 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. All member values are function-supplied. |
| [_ATTRIBUTE_INFO_4 structure](..\winddiui\ns-winddiui-_attribute_info_4.md) | The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. |
| [_ATTRIBUTE_INFO_4 structure](..\winsplp\ns-winsplp-_attribute_info_4.md) | The ATTRIBUTE_INFO_4 structure is used as a parameter for a printer interface DLL's DrvQueryJobAttributes function. |
| [_BIDI_DATA structure](..\winspool\ns-winspool-_bidi_data.md) | The BIDI_DATA structure is used to store the values of a bidi schema. |
| [_BIDI_REQUEST_CONTAINER structure](..\winspool\ns-winspool-_bidi_request_container.md) | The BIDI_REQUEST_CONTAINER structure is a container for a list of bidi requests. |
| [_BIDI_REQUEST_DATA structure](..\winspool\ns-winspool-_bidi_request_data.md) | The BIDI_REQUEST_DATA structure holds a single bidi request. |
| [_BIDI_RESPONSE_CONTAINER structure](..\winspool\ns-winspool-_bidi_response_container.md) | The BIDI_RESPONSE_CONTAINER structure is a container for a list of bidi responses. |
| [_BIDI_RESPONSE_DATA structure](..\winspool\ns-winspool-_bidi_response_data.md) | The BIDI_RESPONSE_DATA structure holds a single bidi response. |
| [_BINARY_CONTAINER structure](..\winspool\ns-winspool-_binary_container.md) | The BINARY_CONTAINER structure is a container for binary data. |
| [_COMPROPSHEETUI structure](..\compstui\ns-compstui-_compropsheetui.md) | The COMPROPSHEETUI structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_ADD_PCOMPROPSHEETUI. All structure members must be supplied by the caller of ComPropSheet. |
| [_CONFIG_INFO_DATA_1 structure](..\tcpxcv\ns-tcpxcv-_config_info_data_1.md) | The XcvData function uses a CONFIG_INFO_DATA_1 structure when it obtains configuration data for a particular port. |
| [_CPSUICBPARAM structure](..\compstui\ns-compstui-_cpsuicbparam.md) | The CPSUICBPARAM structure is used as the input parameter to _CPSUICALLBACK-typed callback functions. |
| [_CPSUIDATABLOCK structure](..\compstui\ns-compstui-_cpsuidatablock.md) | The CPSUIDATABLOCK structure is used as a parameter for the ComPropSheet function, if the function code is CPSFUNC_SET_DATABLOCK or CPSFUNC_QUERY_DATABLOCK. |
| [_CUSTOMSIZEPARAM structure](..\printoem\ns-printoem-_customsizeparam.md) | The CUSTOMSIZEPARAM structure holds information pertaining to a single custom page size parameter for a printer. |
| [_DATA_HEADER structure](..\prntfont\ns-prntfont-_data_header.md) | The DATA_HEADER structure is used to specify a data section within a Unidrv font format file (.uff file). |
| [_DELETE_PORT_DATA_1 structure](..\tcpxcv\ns-tcpxcv-_delete_port_data_1.md) | The XcvData function uses a DELETE_PORT_DATA_1 structure when it deletes a port. |
| [_DEVICEPROPERTYHEADER structure](..\winddiui\ns-winddiui-_devicepropertyheader.md) | The DEVICEPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDevicePropertySheets function. |
| [_DEVOBJ structure](..\printoem\ns-printoem-_devobj.md) | The DEVOBJ structure is used as an input argument to several of a rendering plug-in's COM interface methods. |
| [_DEVQUERYPRINT_INFO structure](..\winddiui\ns-winddiui-_devqueryprint_info.md) | The DEVQUERYPRINT_INFO structure is used as an input parameter to a printer interface DLL's DevQueryPrintEx function. |
| [_DLGPAGE structure](..\compstui\ns-compstui-_dlgpage.md) | The DLGPAGE structure is used for specifying a property sheet page to CPSUI's ComPropSheet function. The structure's address is included in a COMPROPSHEETUI structure, and all member values are supplied by the ComPropSheet caller. |
| [_DOCEVENT_CREATEDCPRE structure](..\winddiui\ns-winddiui-_docevent_createdcpre.md) | The DOCEVENT_CREATEDCPRE structure contains a set of values used in certain calls to DrvDocumentEvent and IPrintOemUI2 |
| [_DOCEVENT_ESCAPE structure](..\winddiui\ns-winddiui-_docevent_escape.md) | The DOCEVENT_ESCAPE structure is a container for values used as parameters for the ExtEscape function. |
| [_DOCEVENT_FILTER structure](..\winddiui\ns-winddiui-_docevent_filter.md) | The DOCEVENT_FILTER structure contains a list of document events to which the printer driver will respond. See DrvDocumentEvent for a complete list of the document events. |
| [_DOCUMENTPROPERTYHEADER structure](..\winddiui\ns-winddiui-_documentpropertyheader.md) | The DOCUMENTPROPERTYHEADER structure is used as an input parameter to a printer interface DLL's DrvDocumentPropertySheets function. |
| [_DOT4_ACTIVITY structure](..\d4iface\ns-d4iface-_dot4_activity.md) | "." |
| [_DOT4_DC_CREATE_DATA structure](..\d4drvif\ns-d4drvif-_dot4_dc_create_data.md) | Defines the DOT4_DC_CREATE_DATA construct. |
| [_DOT4_DC_DESTROY_DATA structure](..\d4drvif\ns-d4drvif-_dot4_dc_destroy_data.md) | This topic describes the DOT4_DC_DESTROY_DATA structure. |
| [_DOT4_DC_OPEN_DATA structure](..\d4drvif\ns-d4drvif-_dot4_dc_open_data.md) | This topic describes the DOT4_DC_OPEN_DATA structure. |
| [_DOT4_DRIVER_CMD structure](..\d4drvif\ns-d4drvif-_dot4_driver_cmd.md) | This topic describes the DOT4_DRIVER_CMD structure. |
| [_DRIVER_INFO_8A structure](..\winspool\ns-winspool-_driver_info_8a.md) | The DRIVER_INFO_8 structure contains printer driver information. |
| [_DRIVER_INFO_8W structure](..\winspool\ns-winspool-_driver_info_8w.md) | The DRIVER_INFO_8 structure contains printer driver information. |
| [_DRIVER_UPGRADE_INFO_1 structure](..\winddiui\ns-winddiui-_driver_upgrade_info_1.md) | The DRIVER_UPGRADE_INFO_1 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
| [_DRIVER_UPGRADE_INFO_2 structure](..\winddiui\ns-winddiui-_driver_upgrade_info_2.md) | The DRIVER_UPGRADE_INFO_2 structure is used as an input to a printer interface DLL's DrvUpgradePrinter function. |
| [_DRVPROCS structure](..\printoem\ns-printoem-_drvprocs.md) | The DRVPROCS structure is obsolete and is not used with the COM interfaces for Microsoft printer drivers. |
| [_EXTCHKBOX structure](..\compstui\ns-compstui-_extchkbox.md) | The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option. |
| [_EXTPUSH structure](..\compstui\ns-compstui-_extpush.md) | The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed. |
| [_EXTTEXTMETRIC structure](..\prntfont\ns-prntfont-_exttextmetric.md) | The EXTTEXTMETRIC structure is used to specify font-specific information within Unidrv font metrics files (.ufm files). |
| [_FINVOCATION structure](..\printoem\ns-printoem-_finvocation.md) | The FINVOCATION structure is used as input to the IPrintOemUni |
| [_GETINFO_FONTOBJ structure](..\printoem\ns-printoem-_getinfo_fontobj.md) | The GETINFO_FONTOBJ structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GETINFO_GLYPHBITMAP structure](..\printoem\ns-printoem-_getinfo_glyphbitmap.md) | The GETINFO_GLYPHBITMAP structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GETINFO_GLYPHSTRING structure](..\printoem\ns-printoem-_getinfo_glyphstring.md) | The GETINFO_GLYPHSTRING structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GETINFO_GLYPHWIDTH structure](..\printoem\ns-printoem-_getinfo_glyphwidth.md) | The GETINFO_GLYPHWIDTH structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GETINFO_MEMORY structure](..\printoem\ns-printoem-_getinfo_memory.md) | The GETINFO_MEMORY structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GETINFO_STDVAR structure](..\printoem\ns-printoem-_getinfo_stdvar.md) | The GETINFO_STDVAR structure is used as input to the UNIFONTOBJ_GetInfo callback function. |
| [_GLYPHRUN structure](..\prntfont\ns-prntfont-_glyphrun.md) | The GLYPHRUN structure is one of the structures used to define the contents of glyph translation table files (.gtt files). |
| [_INSERTPSUIPAGE_INFO structure](..\compstui\ns-compstui-_insertpsuipage_info.md) | The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller. |
| [_INVOC structure](..\prntfont\ns-prntfont-_invoc.md) | The INVOC structure is used for describing printer command strings in Unidrv font metrics files (.ufm files) and glyph translation table files (.gtt files). |
| [_KERNDATA structure](..\prntfont\ns-prntfont-_kerndata.md) | The KERNDATA structure is used for describing printer kerning pairs. |
| [_MAPTABLE structure](..\prntfont\ns-prntfont-_maptable.md) | The MAPTABLE structure is one of the structures used to define the contents of glyph translation table files (.gtt files). |
| [_MONITOR structure](..\winsplp\ns-winsplp-_monitor.md) | The MONITOR structure is obsolete and is supported only for compatibility reasons. |
| [_MONITOR2 structure](..\winsplp\ns-winsplp-_monitor2.md) | The MONITOR2 structure contains pointers to the functions defined by print monitors. |
| [_MONITOREX structure](..\winsplp\ns-winsplp-_monitorex.md) | The MONITOREX structure is obsolete and supported for compatibility purposes only. |
| [_MONITORINIT structure](..\winsplp\ns-winsplp-_monitorinit.md) | The MONITORINIT structure is used as an input parameter to a print monitor's InitializePrintMonitor2 function. |
| [_MONITORREG structure](..\winsplp\ns-winsplp-_monitorreg.md) | The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions. |
| [_MONITORUI structure](..\winsplp\ns-winsplp-_monitorui.md) | The MONITORUI structure contains pointers to the functions within a port monitor UI DLL that the print spooler calls. |
| [_NOTIFICATION_CONFIG_1 structure](..\winsplp\ns-winsplp-_notification_config_1.md) | "." |
| [_OEMCUIPPARAM structure](..\printoem\ns-printoem-_oemcuipparam.md) | The OEMCUIPPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI |
| [_OEMDMPARAM structure](..\printoem\ns-printoem-_oemdmparam.md) | The OEMDMPARAM structure is used as an input parameter to the IPrintOemUI |
| [_OEMFONTINSTPARAM structure](..\prntfont\ns-prntfont-_oemfontinstparam.md) | The OEMFONTINSTPARAM structure is used as an input parameter to a user interface plug-in's IPrintOemUI |
| [_OEMUIOBJ structure](..\printoem\ns-printoem-_oemuiobj.md) | The OEMUIOBJ structure is used as an input argument to several of the methods exported by user interface plug-ins. |
| [_OEMUIPROCS structure](..\printoem\ns-printoem-_oemuiprocs.md) | The OEMUIPROCS structure is obsolete.The OEMUIPROCS structure contains the address of the DrvGetDriverSetting and DrvUpdateUISetting functions that are exported by Microsoft printer drivers. |
| [_OEMUIPSPARAM structure](..\printoem\ns-printoem-_oemuipsparam.md) | The OEMUIPSPARAM structure is passed to a user interface plug-in's IPrintOemUI |
| [_OEM_DMEXTRAHEADER structure](..\printoem\ns-printoem-_oem_dmextraheader.md) | The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private DEVMODEW structure members. |
| [_OIEXT structure](..\compstui\ns-compstui-_oiext.md) | The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure. |
| [_OPTCOMBO structure](..\compstui\ns-compstui-_optcombo.md) | "." |
| [_OPTITEM structure](..\compstui\ns-compstui-_optitem.md) | The OPTITEM structure is used by CPSUI applications (including printer interface DLLs) for describing one property sheet option on a property sheet page, if the page is described by a COMPROPSHEETUI structure. |
| [_OPTPARAM structure](..\compstui\ns-compstui-_optparam.md) | An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure. |
| [_OPTTYPE structure](..\compstui\ns-compstui-_opttype.md) | The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure. |
| [_PDEV_ADJUST_GRAPHICS_RESOLUTION structure](..\printoem\ns-printoem-_pdev_adjust_graphics_resolution.md) | The PDEV_ADJUST_GRAPHICS_RESOLUTION structure specifies a graphics resolution value. |
| [_PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure](..\printoem\ns-printoem-_pdev_adjust_imageable_origin_area.md) | The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area. |
| [_PDEV_ADJUST_PAPER_MARGIN structure](..\printoem\ns-printoem-_pdev_adjust_paper_margin.md) | The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area. |
| [_PDEV_ADJUST_PHYSICAL_PAPER_SIZE structure](..\printoem\ns-printoem-_pdev_adjust_physical_paper_size.md) | The PDEV_ADJUST_PAPER_PHYSICAL_SIZE structure specifies a paper size value. |
| [_PDEV_HOSTFONT_ENABLED structure](..\printoem\ns-printoem-_pdev_hostfont_enabled.md) | The PDEV_HOSTFONT_ENABLED structure indicates whether the Hostfont feature is enabled. |
| [_PDEV_USE_TRUE_COLOR structure](..\printoem\ns-printoem-_pdev_use_true_color.md) | The PDEV_USE_TRUE_COLOR structure indicates whether the output color space should be color or grayscale. |
| [_PORT_DATA_1 structure](..\tcpxcv\ns-tcpxcv-_port_data_1.md) | The XcvData function uses a PORT_DATA_1 structure when it adds a port or configures an existing port. |
| [_PRINTER_EVENT_ATTRIBUTES_INFO structure](..\winddiui\ns-winddiui-_printer_event_attributes_info.md) | The PRINTER_EVENT_ATTRIBUTES_INFO structure contains the former attributes and the new attributes for a printer. |
| [_PRINTER_NOTIFY_INIT structure](..\winsplp\ns-winsplp-_printer_notify_init.md) | "." |
| [_PRINTPROCESSOROPENDATA structure](..\winsplp\ns-winsplp-_printprocessoropendata.md) | The PRINTPROCESSOROPENDATA structure is used as an input parameter to a print processor's OpenPrintProcessor function. |
| [_PRINTPROVIDOR structure](..\winsplp\ns-winsplp-_printprovidor.md) | Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated. |
| [_PRINT_FEATURE_OPTION structure](..\prcomoem\ns-prcomoem-_print_feature_option.md) | The PRINT_FEATURE_OPTION structure contains information about a feature-option pair, where the option is one option of a particular feature. |
| [_PROPSHEETUI_GETICON_INFO structure](..\compstui\ns-compstui-_propsheetui_geticon_info.md) | The PROPSHEETUI_GETICON_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_ICON. |
| [_PROPSHEETUI_INFO structure](..\compstui\ns-compstui-_propsheetui_info.md) | The PROPSHEETUI_INFO structure is used as an input parameter to PFNPROPSHEETUI-typed functions. |
| [_PROPSHEETUI_INFO_HEADER structure](..\compstui\ns-compstui-_propsheetui_info_header.md) | The PROPSHEETUI_INFO_HEADER structure is used as an input parameter to an application's PFNPROPSHEETUI-typed function, when the function is called with a reason value of PROPSHEETUI_REASON_GET_INFO_HEADER. |
| [_PSCRIPT5_PRIVATE_DEVMODE structure](..\printoem\ns-printoem-_pscript5_private_devmode.md) | The PSCRIPT5_PRIVATE_DEVMODE structure enables Pscript5 plug-ins to determine the size of the private portion of Pscript5's DEVMODEW structure. |
| [_PSPINFO structure](..\compstui\ns-compstui-_pspinfo.md) | The PSPINFO structure is used as an input parameter to a property sheet page's dialog box procedure, when the Windows message is WM_INITDIALOG. The dialog box procedure's address is specified in a DLGPAGE structure. |
| [_PUBLISHERINFO structure](..\printoem\ns-printoem-_publisherinfo.md) | The PUBLISHERINFO structure is used as an input parameter to the IPrintOemPS |
| [_SETRESULT_INFO structure](..\compstui\ns-compstui-_setresult_info.md) | The SETRESULT_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed callback function. |
| [_SIMULATE_CAPS_1 structure](..\printoem\ns-printoem-_simulate_caps_1.md) | The SIMULATE_CAPS_1 structure contains information about the types of simulations a spooler supports. |
| [_SPLCLIENT_INFO_1 structure](..\winsplp\ns-winsplp-_splclient_info_1.md) | The SPLCLIENT_INFO_1 structure is used as input to the GenerateCopyFilePaths function that is exported by Point and Print DLLs. |
| [_SPLCLIENT_INFO_2_V1 structure](..\winsplp\ns-winsplp-_splclient_info_2_v1.md) | Contains the handle for the server-side printer that is used to make direct API calls from the client to the server without the overhead of the RPC. |
| [_SPLCLIENT_INFO_2_V2 structure](..\winsplp\ns-winsplp-_splclient_info_2_v2.md) | "." |
| [_SPLCLIENT_INFO_2_V3 structure](..\winsplp\ns-winsplp-_splclient_info_2_v3.md) | "." |
| [_SPLCLIENT_INFO_3_VISTA structure](..\winsplp\ns-winsplp-_splclient_info_3_vista.md) | Contains a super-set of the information in both a SPLCLIENT_INFO_1 and SPLCLIENT_INFO_2 structure. It also contains additional information needed by the provider. |
| [_TRANSDATA structure](..\prntfont\ns-prntfont-_transdata.md) | The TRANSDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files). |
| [_UFF_FILEHEADER structure](..\prntfont\ns-prntfont-_uff_fileheader.md) | The UFF_FILEHEADER structure is used to define the contents of Unidrv font format files (.uff files). |
| [_UFF_FONTDIRECTORY structure](..\prntfont\ns-prntfont-_uff_fontdirectory.md) | The UFF_FONTDIRECTORY structure is used to specify the directory of font descriptions contained in a Unidrv font format file (.uff file). |
| [_UNIDRVINFO structure](..\prntfont\ns-prntfont-_unidrvinfo.md) | The UNIDRVINFO structure is used to specify printer-specific information within Unidrv font metrics files (.ufm files). |
| [_UNIDRV_PRIVATE_DEVMODE structure](..\printoem\ns-printoem-_unidrv_private_devmode.md) | The UNIDRV_PRIVATE_DEVMODE structure enables Unidrv plug-ins to determine the size of the private portion of Unidrv's DEVMODEW structure. |
| [_UNIFM_HDR structure](..\prntfont\ns-prntfont-_unifm_hdr.md) | The UNIFM_HDR structure is used to define the contents of Unidrv font metrics files (.ufm files). |
| [_UNIFONTOBJ structure](..\printoem\ns-printoem-_unifontobj.md) | The UNIFONTOBJ structure is used as an input parameter to font functions in rendering plug-ins. |
| [_UNI_CODEPAGEINFO structure](..\prntfont\ns-prntfont-_uni_codepageinfo.md) | The UNI_CODEPAGEINFO structure is one of the structures used to define the contents of glyph translation table files (.gtt files). |
| [_UNI_GLYPHSETDATA structure](..\prntfont\ns-prntfont-_uni_glyphsetdata.md) | The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files). |
| [_USERDATA structure](..\printoem\ns-printoem-_userdata.md) | The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure. |
| [_WIDTHRUN structure](..\prntfont\ns-prntfont-_widthrun.md) | The WIDTHRUN structure is used to define the contents of Unidrv font metrics files (.ufm files). |
| [_WIDTHTABLE structure](..\prntfont\ns-prntfont-_widthtable.md) | The WIDTHTABLE structure is used to define the contents of Unidrv font metrics files (.ufm files). |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [BIDI_TYPE enumeration](..\winspool\ne-winspool-bidi_type.md) | The BIDI_TYPE enumeration lists the possible values of data transferred in a bidi operation. |
| [BMFORMAT enumeration](..\icm\ne-icm-bmformat.md) | The values of the BMFORMAT enumeration are used by WCS functions to indicate the format that particular bitmaps are in. This data type is extended from BMFORMAT that is available in versions of Windows released before Windows Vista. |
| [COLORDATATYPE enumeration](..\icm\ne-icm-colordatatype.md) | The values of the COLORDATATYPE enumeration are used by WCS functions to indicate the data type of vector content. |
| [COLORPROFILESUBTYPE enumeration](..\icm\ne-icm-colorprofilesubtype.md) | The COLORPROFILESUBTYPE enumeration is used to specify the subtype of color profile. |
| [COLORPROFILETYPE enumeration](..\icm\ne-icm-colorprofiletype.md) | The COLORPROFILETYPE enumeration is used to specify the type of color profile. |
| [COLORTYPE enumeration](..\icm\ne-icm-colortype.md) | The values of the COLORTYPE enumeration are used by WCS functions to indicate the format of vector content. Most values have equivalent structures that are contained in the ICM COLOR structure (described in the Microsoft Windows SDK documentation). |
| [UI_TYPE enumeration](..\winsplp\ne-winsplp-ui_type.md) | "." |
| [WCS_PROFILE_MANAGEMENT_SCOPE enumeration](..\icm\ne-icm-wcs_profile_management_scope.md) | The WCS_PROFILE_MANAGEMENT_SCOPE enumeration is used to specify the scope of a profile management operation, such as associating a profile with a device. |
| [_EATTRIBUTE_DATATYPE enumeration](..\printoem\ne-printoem-_eattribute_datatype.md) | The EATTRIBUTE_DATATYPE enumerates the possible data types for a global attribute, feature attribute or option attribute. |
| [_NOTIFICATION_CALLBACK_COMMANDS enumeration](..\winsplp\ne-winsplp-_notification_callback_commands.md) | "." |
| [_NOTIFICATION_CONFIG_FLAGS enumeration](..\winsplp\ne-winsplp-_notification_config_flags.md) | "." |
| [_STDVARIABLEINDEX enumeration](..\printoem\ne-printoem-_stdvariableindex.md) | "." |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0001 enumeration](..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0001.md) | The ExpsCompressionOptions enumeration describes compression options for an XPS part. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0002 enumeration](..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0002.md) | The EXpsFontOptions enumeration describes the font options for an XPS part. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0003 enumeration](..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003.md) | The EXpsJobConsumption enumeration describes job consumption updates. |
| [__MIDL___MIDL_itf_filterpipeline_0000_0000_0004 enumeration](..\filterpipeline\ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0004.md) | "." |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0001_0001 enumeration](..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md) | The XPSRAS_RENDERING_MODE enumeration specifies the rendering mode to be used by an XPS rasterizer. |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0003_0001 enumeration](..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001.md) | XPSRAS_PIXEL_FORMAT allows a caller to select the pixel format used by the IWICBitmap interface that is returned by the IXpsRasterizer |
| [__MIDL___MIDL_itf_xpsrassvc_0000_0004_0001 enumeration](..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0004_0001.md) | XPSRAS_BACKGROUND_COLOR specifies the background clear color to be used by an XPS rasterizer |
| [tagOEMPTOPTS enumeration](..\prcomoem\ne-prcomoem-tagoemptopts.md) | "." |
| [tagPrintJobStatus enumeration](..\printerextension\ne-printerextension-tagprintjobstatus.md) | This enumeration is a one-to-one mapping to the spooler flags suppled in the JOB_INFO_X structures. |
| [tagPrintSchemaConstrainedSetting enumeration](..\printerextension\ne-printerextension-tagprintschemaconstrainedsetting.md) | The PrintSchemaConstrainedSetting enumeration specifies whether the Option is available based on the current device configuration. The constrained attribute appears only in a PrintCapabilities document. |
| [tagPrintSchemaParameterDataType enumeration](..\printerextension\ne-printerextension-tagprintschemaparameterdatatype.md) | The PrintSchemaParameterDataType enumeration identifies the allowed data types for the Print Schema parameter. |
| [tagPrintSchemaSelectionType enumeration](..\printerextension\ne-printerextension-tagprintschemaselectiontype.md) | The PrintSchemaSelectionType enumeration identifies how a Feature’s options should be selected. This property appears only in a PrintCapabilities document. |
| [tagSHIMOPTS enumeration](..\prdrvcom\ne-prdrvcom-tagshimopts.md) | "." |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_DOT4_ADD_ACTIVITY_BROADCAST IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_add_activity_broadcast.md) | This topic describes IOCTL_DOT4_ADD_ACTIVITY_BROADCAST. |
| [IOCTL_DOT4_CLOSE_CHANNEL IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_close_channel.md) | This topic describes IOCTL_DOT4_CLOSE_CHANNEL. |
| [IOCTL_DOT4_CREATE_SOCKET IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_create_socket.md) | This topic describes IOCTL_DOT4_CREATE_SOCKET. |
| [IOCTL_DOT4_DESTROY_SOCKET IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_destroy_socket.md) | This topic describes IOCTL_DOT4_DESTROY_SOCKET. |
| [IOCTL_DOT4_LAST IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_last.md) | This topic describes IOCTL_DOT4_LAST. |
| [IOCTL_DOT4_OPEN_CHANNEL IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_open_channel.md) | This topic describes IOCTL_DOT4_OPEN_CHANNEL. |
| [IOCTL_DOT4_READ IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_read.md) | This topic describes IOCTL_DOT4_READ. |
| [IOCTL_DOT4_REMOVE_ACTIVITY_BROADCAST IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_remove_activity_broadcast.md) | This topic describes IOCTL_DOT4_REMOVE_ACTIVITY_BROADCAST. |
| [IOCTL_DOT4_USER_BASE IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_user_base.md) | This topic describes IOCTL_DOT4_USER_BASE. |
| [IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_wait_activity_broadcast.md) | This topic describes IOCTL_DOT4_WAIT_ACTIVITY_BROADCAST. |
| [IOCTL_DOT4_WAIT_FOR_CHANNEL IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_wait_for_channel.md) | This topic describes IOCTL_DOT4_WAIT_FOR_CHANNEL. |
| [IOCTL_DOT4_WRITE IOCTL](..\d4drvif\ni-d4drvif-ioctl_dot4_write.md) | This topic describes IOCTL_DOT4_WRITE. |
| [IOCTL_USBPRINT_GET_1284_ID IOCTL](..\usbprint\ni-usbprint-ioctl_usbprint_get_1284_id.md) | The IOCTL_USBPRINT_GET_1284_ID control code allows upper-layer software (such as a language monitor), to request and obtain the printer's IEEE 1284 device ID string. |
| [IOCTL_USBPRINT_GET_LPT_STATUS IOCTL](..\usbprint\ni-usbprint-ioctl_usbprint_get_lpt_status.md) | The IOCTL_USBPRINT_GET_LPT_STATUS request allows upper-layer software (such as a language monitor), to request and obtain the printer status byte from a USB printer. |
| [IOCTL_USBPRINT_SOFT_RESET IOCTL](..\usbprint\ni-usbprint-ioctl_usbprint_soft_reset.md) | The IOCTL_USBPRINT_SOFT_RESET request allows upper-layer software (such as a language monitor), to issue a class-specific soft reset command to the printer. |
| [IOCTL_USBPRINT_VENDOR_GET_COMMAND IOCTL](..\usbprint\ni-usbprint-ioctl_usbprint_vendor_get_command.md) | The IOCTL_USBPRINT_VENDOR_GET_COMMAND request allows upper-layer software (such as a language monitor), to issue a vendor-specific GET command to the target device. |
| [IOCTL_USBPRINT_VENDOR_SET_COMMAND IOCTL](..\usbprint\ni-usbprint-ioctl_usbprint_vendor_set_command.md) | The IOCTL_USBPRINT_VENDOR_SET_COMMAND request allows upper-layer software (such as a language monitor) to issue a vendor-specific SET command to the target device. |

## Interfaces

| Title   | Description   |
| ---- |:---- |
| [IAsyncGetSendNotificationCookie interface](..\prnasntp\nn-prnasntp-iasyncgetsendnotificationcookie.md) | "." |
| [IAsyncGetSrvReferralCookie interface](..\prnasntp\nn-prnasntp-iasyncgetsrvreferralcookie.md) | "." |
| [IBidiAsyncNotifyChannel interface](..\prnasntp\nn-prnasntp-ibidiasyncnotifychannel.md) | "." |
| [IBidiRequest interface](..\bidispl\nn-bidispl-ibidirequest.md) | The IBidiRequest interface allows an application or other objects to compose a bidi request. |
| [IBidiRequestContainer interface](..\bidispl\nn-bidispl-ibidirequestcontainer.md) | The IBidiRequestContainer interface allows an application or other objects to compose and retrieve a list of bidi requests. |
| [IBidiSpl interface](..\bidispl\nn-bidispl-ibidispl.md) | The IBidiSpl interface allows an application or other objects to send a single bidi request or a list of bidi requests. |
| [IBidiSpl2 interface](..\bidispl\nn-bidispl-ibidispl2.md) | The IBidiSpl2 interface enables an application or other objects to send one or more bidi requests using one of the Bidi Request Schemas and receive information formatted as one of the Bidi Response Schemas. |
| [IFixedDocument interface](..\filterpipeline\nn-filterpipeline-ifixeddocument.md) | The IFixedDocument interface represents a fixed document for an XPS document sequence. |
| [IFixedDocumentSequence interface](..\filterpipeline\nn-filterpipeline-ifixeddocumentsequence.md) | The IFixedDocumentSequence interface represents the fixed document sequence for an XPS document. |
| [IFixedPage interface](..\filterpipeline\nn-filterpipeline-ifixedpage.md) | A filter uses the IFixedPage interface to work with fixed pages in an XPS document. |
| [IInterFilterCommunicator interface](..\filterpipeline\nn-filterpipeline-iinterfiltercommunicator.md) | The IInterFilterCommunicator interface is implemented in an object that resides in the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. |
| [IPartBase interface](..\filterpipeline\nn-filterpipeline-ipartbase.md) | The IPartBase interface is a common base for document part interfaces. |
| [IPartColorProfile interface](..\filterpipeline\nn-filterpipeline-ipartcolorprofile.md) | The IPartColorProfile interface is the abstraction for an XPS color profile. |
| [IPartDiscardControl interface](..\filterpipeline\nn-filterpipeline-ipartdiscardcontrol.md) | The filter pipeline supports the discard control. |
| [IPartFont interface](..\filterpipeline\nn-filterpipeline-ipartfont.md) | The IPartFont interface is the abstraction for fonts in a part. |
| [IPartFont2 interface](..\filterpipeline\nn-filterpipeline-ipartfont2.md) | "." |
| [IPartImage interface](..\filterpipeline\nn-filterpipeline-ipartimage.md) | The IPartImage interface is the abstraction for images in an XPS document. |
| [IPartPrintTicket interface](..\filterpipeline\nn-filterpipeline-ipartprintticket.md) | The IPartPrintTicket interface is the abstraction for a print ticket in an XPS document. |
| [IPartResourceDictionary interface](..\filterpipeline\nn-filterpipeline-ipartresourcedictionary.md) | The IPartResourceDictionary interface is the abstraction for an XPS resource dictionary. |
| [IPartThumbnail interface](..\filterpipeline\nn-filterpipeline-ipartthumbnail.md) | The IPartThumbnail interface is an abstraction for thumbnails in an XPS document. |
| [IPrintAsyncCookie interface](..\prnasntp\nn-prnasntp-iprintasynccookie.md) | "." |
| [IPrintAsyncNewChannelCookie interface](..\prnasntp\nn-prnasntp-iprintasyncnewchannelcookie.md) | "." |
| [IPrintAsyncNotify interface](..\prnasntp\nn-prnasntp-iprintasyncnotify.md) | "." |
| [IPrintAsyncNotifyRegistration interface](..\prnasntp\nn-prnasntp-iprintasyncnotifyregistration.md) | "." |
| [IPrintAsyncNotifyServerReferral interface](..\prnasntp\nn-prnasntp-iprintasyncnotifyserverreferral.md) | "." |
| [IPrintBidiAsyncNotifyRegistration interface](..\prnasntp\nn-prnasntp-iprintbidiasyncnotifyregistration.md) | "." |
| [IPrintClassObjectFactory interface](..\filterpipeline\nn-filterpipeline-iprintclassobjectfactory.md) | TheIPrintClassObjectFactory interface creates print filter-related interfaces. |
| [IPrintCoreHelper interface](..\prcomoem\nn-prcomoem-iprintcorehelper.md) | This section describes the methods that are defined for the IPrintCoreHelper COM interface. |
| [IPrintCoreHelperPS interface](..\prcomoem\nn-prcomoem-iprintcorehelperps.md) | This section describes the methods that are defined for the IPrintCoreHelperPS COM interface. |
| [IPrintCoreHelperUni interface](..\prcomoem\nn-prcomoem-iprintcorehelperuni.md) | This section describes the methods that are defined for the IPrintCoreHelperUni COM interface. |
| [IPrintCoreHelperUni2 interface](..\prcomoem\nn-prcomoem-iprintcorehelperuni2.md) | The IPrintCoreHelperUni2 interface derives from the IPrintCoreHelperUni interface and adds a method. |
| [IPrintCorePS2 interface](..\prcomoem\nn-prcomoem-iprintcoreps2.md) | This section describes the methods defined for the IPrintCorePS2 COM Interface. Method prototypes are defined in prcomoem.h. |
| [IPrintCoreUI2 interface](..\prcomoem\nn-prcomoem-iprintcoreui2.md) | This section describes the methods defined for the IPrintCoreUI2 COM Interface. |
| [IPrintJob interface](..\printerextension\nn-printerextension-iprintjob.md) | Contains properties that represent a print job. |
| [IPrintJobCollection interface](..\printerextension\nn-printerextension-iprintjobcollection.md) | This interfaces provides an enumeration of the jobs in the print queue. |
| [IPrintOemDriverPS interface](..\prcomoem\nn-prcomoem-iprintoemdriverps.md) | This section describes the methods defined for the IPrintOemDriverPS COM Interface. |
| [IPrintOemDriverUI interface](..\prcomoem\nn-prcomoem-iprintoemdriverui.md) | This section describes the methods defined for the IPrintOemDriverUI COM Interface. |
| [IPrintOemDriverUni interface](..\prcomoem\nn-prcomoem-iprintoemdriveruni.md) | This section describes the methods defined for the IPrintOemDriverUni COM interface. |
| [IPrintOemEngine interface](..\prcomoem\nn-prcomoem-iprintoemengine.md) | "." |
| [IPrintOemPS interface](..\prcomoem\nn-prcomoem-iprintoemps.md) | This section describes the methods defined for the IPrintOemPS COM interface. |
| [IPrintOemPS2 interface](..\prcomoem\nn-prcomoem-iprintoemps2.md) | This section describes the methods defined for the IPrintOemPS2 COM interface. In addition to these methods, this interface includes all of the methods defined in the IPrintOemPS COM interface. |
| [IPrintOemPrintTicketProvider interface](..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md) | This section describes the methods that are defined for the IPrintOemPrintTicketProvider COM interface. |
| [IPrintOemUI interface](..\prcomoem\nn-prcomoem-iprintoemui.md) | This section describes the methods defined for the IPrintOemUI COM interface. |
| [IPrintOemUI2 interface](..\prcomoem\nn-prcomoem-iprintoemui2.md) | This section describes the methods defined for the IPrintOemUI2 COM interface. |
| [IPrintOemUIMXDC interface](..\prcomoem\nn-prcomoem-iprintoemuimxdc.md) | This section describes the methods that are defined for the IPrintOemUIMXDC COM interface. |
| [IPrintOemUni interface](..\prcomoem\nn-prcomoem-iprintoemuni.md) | This section describes the methods defined for the IPrintOemUni COM interface. |
| [IPrintOemUni2 interface](..\prcomoem\nn-prcomoem-iprintoemuni2.md) | This section describes the methods defined for the IPrintOemUni2 COM interface. |
| [IPrintOemUni3 interface](..\prcomoem\nn-prcomoem-iprintoemuni3.md) | This section describes the methods defined for the IPrintOemUni3 COM interface. |
| [IPrintPipelineFilter interface](..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md) | The methods in the IPrintPipelineFilter interface are called for initialization and shutdown. A filter must implement these methods. |
| [IPrintPipelineManagerControl interface](..\filterpipeline\nn-filterpipeline-iprintpipelinemanagercontrol.md) | The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter |
| [IPrintPipelineProgressReport interface](..\filterpipeline\nn-filterpipeline-iprintpipelineprogressreport.md) | A rendering filter uses the IPrintPipelineProgressReport interface to send progress status to a spooler. |
| [IPrintPipelinePropertyBag interface](..\filterpipeline\nn-filterpipeline-iprintpipelinepropertybag.md) | The IPrintPipelinePropertyBag interface is implemented by the PrintFilterPipelineSvc service and is made available to filters through methods in the IPrintPipelineFilter interface. IprintPipelinePropertyBag inherits from the IUnknown interface. |
| [IPrintReadStream interface](..\filterpipeline\nn-filterpipeline-iprintreadstream.md) | Filters use the IPrintReadStream interface to read data as a raw stream of bytes. |
| [IPrintReadStreamFactory interface](..\filterpipeline\nn-filterpipeline-iprintreadstreamfactory.md) | The IPrintReadStreamFactory interface creates a stream reader that a filter can use to access the stream. For example, a filter could use this stream to access the per-user print ticket. |
| [IPrintSchemaAsyncOperation interface](..\printerextension\nn-printerextension-iprintschemaasyncoperation.md) | Represents an asynchronous operation context for validation, merge or commit operations. |
| [IPrintSchemaAsyncOperationEvent interface](..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md) | Exposes a validation, merge, or commit completion event delegate. |
| [IPrintSchemaCapabilities interface](..\printerextension\nn-printerextension-iprintschemacapabilities.md) | Provides the primary method to access PrintCapabilities. |
| [IPrintSchemaCapabilities2 interface](..\printerextension\nn-printerextension-iprintschemacapabilities2.md) | The IPrintSchemaCapabilities2 interface represents an extension to the IPrintSchemaCapabilities object, which provides wrapper methods over a print capabilities document. |
| [IPrintSchemaDisplayableElement interface](..\printerextension\nn-printerextension-iprintschemadisplayableelement.md) | Provides the displayable string for a PrintCapabilites PrintSchema element. |
| [IPrintSchemaElement interface](..\printerextension\nn-printerextension-iprintschemaelement.md) | Provides access to the underlying XML node and &#0034;name&#0034; attribute information for a Print Schema element. |
| [IPrintSchemaFeature interface](..\printerextension\nn-printerextension-iprintschemafeature.md) | Exposes a Print Schema Feature element. |
| [IPrintSchemaNUpOption interface](..\printerextension\nn-printerextension-iprintschemanupoption.md) | Exposes a Print Schema NUp Option element. |
| [IPrintSchemaOption interface](..\printerextension\nn-printerextension-iprintschemaoption.md) | Exposes a Print Schema Option object. |
| [IPrintSchemaOptionCollection interface](..\printerextension\nn-printerextension-iprintschemaoptioncollection.md) | Exposes a collection of IPrintSchemaOption objects. |
| [IPrintSchemaPageImageableSize interface](..\printerextension\nn-printerextension-iprintschemapageimageablesize.md) | Exposes the PageImageableSize property of PrintCapabilities. The properties of this interface map directly to those in the PageImageableSize property of PrintCapabilities. |
| [IPrintSchemaPageMediaSizeOption interface](..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md) | Exposes a Print Schema PageMediaSize Option element. |
| [IPrintSchemaParameterDefinition interface](..\printerextension\nn-printerextension-iprintschemaparameterdefinition.md) | The IPrintSchemaParameterDefinition interface represents a parameter definition, as defined in the Print Schema Specification. |
| [IPrintSchemaParameterInitializer interface](..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md) | The IPrintSchemaParameterInitializer interface represents a parameter initialization value, as defined in the print schema specification. |
| [IPrintSchemaTicket interface](..\printerextension\nn-printerextension-iprintschematicket.md) | Provides the primary method to access and validate a PrintTicket. |
| [IPrintSchemaTicket2 interface](..\printerextension\nn-printerextension-iprintschematicket2.md) | The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document. |
| [IPrintUnidiAsyncNotifyRegistration interface](..\prnasntp\nn-prnasntp-iprintunidiasyncnotifyregistration.md) | Provides information on IPrintUnidiAsyncNotifyRegistration constructs. |
| [IPrintWriteStream interface](..\filterpipeline\nn-filterpipeline-iprintwritestream.md) | Filters use the IPrintWriteStream interface to write data as a raw stream of bytes. |
| [IPrintWriteStreamFlush interface](..\filterpipeline\nn-filterpipeline-iprintwritestreamflush.md) | Filters use the IPrintWriteStreamFlush interface to explicitly flush data as a raw stream of bytes from a filter. This interface is retrieved through IPrintWriteStream |
| [IPrinterBidiSetRequestCallback interface](..\printerextension\nn-printerextension-iprinterbidisetrequestcallback.md) | Describes the signature of the callback object that receives the Bidi response. |
| [IPrinterExtensionAsyncOperation interface](..\printerextension\nn-printerextension-iprinterextensionasyncoperation.md) | Provides the context associated with an asynchronous operation. |
| [IPrinterExtensionContext interface](..\printerextension\nn-printerextension-iprinterextensioncontext.md) | Represents the context for the activation of a UWP device app for printers. |
| [IPrinterExtensionContextCollection interface](..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md) | Exposes a collection of IPrinterExtensionContext objects. |
| [IPrinterExtensionEvent interface](..\printerextension\nn-printerextension-iprinterextensionevent.md) | The IPrinterExtensionEvent interface represents the event delegate implemented by desktop printer extensions for activation. |
| [IPrinterExtensionEventArgs interface](..\printerextension\nn-printerextension-iprinterextensioneventargs.md) | Represents the context for the desktop printer extension activation. |
| [IPrinterExtensionManager interface](..\printerextension\nn-printerextension-iprinterextensionmanager.md) | The IPrinterExtensionManager interface is retrieved by CoCreating the PrinterExtensionManager class. |
| [IPrinterExtensionRequest interface](..\printerextension\nn-printerextension-iprinterextensionrequest.md) | Completes the given extension event with either a cancellation or success. |
| [IPrinterPropertyBag interface](..\printerextension\nn-printerextension-iprinterpropertybag.md) | Provides strongly-typed get and set methods. |
| [IPrinterQueue interface](..\printerextension\nn-printerextension-iprinterqueue.md) | Represents a single printer queue. |
| [IPrinterQueue2 interface](..\printerextension\nn-printerextension-iprinterqueue2.md) | Represents a single printer queue. |
| [IPrinterQueueEvent interface](..\printerextension\nn-printerextension-iprinterqueueevent.md) | Provides the event delegate for printer queue events. |
| [IPrinterQueueView interface](..\printerextension\nn-printerextension-iprinterqueueview.md) | Provides a way to change the range of print jobs being monitored. |
| [IPrinterQueueViewEvent interface](..\printerextension\nn-printerextension-iprinterqueueviewevent.md) | Provides the signature of the event handler. |
| [IPrinterScriptContext interface](..\printerextension\nn-printerextension-iprinterscriptcontext.md) | Passed to all third-party constraints JavaScript functions, and provides access to relevant objects. |
| [IPrinterScriptablePropertyBag interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag.md) | The IPrinterScriptablePropertyBag interface is the property bag interface passed to script clients. |
| [IPrinterScriptablePropertyBag2 interface](..\printerextension\nn-printerextension-iprinterscriptablepropertybag2.md) | "." |
| [IPrinterScriptableSequentialStream interface](..\printerextension\nn-printerextension-iprinterscriptablesequentialstream.md) | The IPrinterScriptableSequentialStream interface is an ISequentialStream-like interface that works in JavaScript. Instead of reading and writing byte arrays, it reads and writes JavaScript arrays of bytes, which are values between 0 and 255. |
| [IPrinterScriptableStream interface](..\printerextension\nn-printerextension-iprinterscriptablestream.md) | The IPrinterScriptableStream interface builds on IPrinterScriptableSequentialStream and adds IStream-like semantics. |
| [IXpsDocument interface](..\filterpipeline\nn-filterpipeline-ixpsdocument.md) | The IXpsDocument interface represents the root of an XPS document. |
| [IXpsDocumentConsumer interface](..\filterpipeline\nn-filterpipeline-ixpsdocumentconsumer.md) | A filter uses the IXpsDocumentConsumer interface when it generates XPS content for the pipeline to consume. |
| [IXpsDocumentProvider interface](..\filterpipeline\nn-filterpipeline-ixpsdocumentprovider.md) | The IxpsDocumentProvider interface provides interfaces to consume parts of a document. |
| [IXpsPartIterator interface](..\filterpipeline\nn-filterpipeline-ixpspartiterator.md) | The IXpsPartIterator interface is an iterator for XPS parts. |
| [IXpsRasterizationFactory interface](..\xpsrassvc\nn-xpsrassvc-ixpsrasterizationfactory.md) | The IXpsRasterizationFactory interface represents an object factory for creating XPS rasterizer objects. |
| [IXpsRasterizationFactory1 interface](..\xpsrassvc\nn-xpsrassvc-ixpsrasterizationfactory1.md) | In Windows 8, the improvement of XPSRas to handle high precision colors has led to the development of a new interface, IXPSRasterizationFactory1. |
| [IXpsRasterizationFactory2 interface](..\xpsrassvc\nn-xpsrassvc-ixpsrasterizationfactory2.md) | In Windows 10, the IXpsRasterizationFactory2 interface represents an object factory for creating components that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |
| [IXpsRasterizer interface](..\xpsrassvc\nn-xpsrassvc-ixpsrasterizer.md) | The IXpsRasterizer interface represents an XPS rasterizer that can create a bitmap image of an XPS fixed page or of a rectangular region of a fixed page. |
| [IXpsRasterizerNotificationCallback interface](..\xpsrassvc\nn-xpsrassvc-ixpsrasterizernotificationcallback.md) | The IXpsRasterizerNotificationCallback interface enables the XPS rasterization service to determine whether to continue a rasterization operation that was previously initiated by an XPSDrv filter. |

## Methods

| Title   | Description   |
| ---- |:---- |
| [IBidiAsyncNotifyChannel::AsyncCloseChannel](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-asyncclosechannel.md) | "." |
| [IBidiAsyncNotifyChannel::AsyncGetNotificationSendResponse](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-asyncgetnotificationsendresponse.md) | "." |
| [IBidiAsyncNotifyChannel::CloseChannel](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-closechannel.md) | "." |
| [IBidiAsyncNotifyChannel::CreateNotificationChannel](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-createnotificationchannel.md) | "." |
| [IBidiAsyncNotifyChannel::GetChannelNotificationType](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-getchannelnotificationtype.md) | "." |
| [IBidiAsyncNotifyChannel::GetPrintName](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-getprintname.md) | "." |
| [IBidiAsyncNotifyChannel::SendNotification](..\prnasntp\nf-prnasntp-ibidiasyncnotifychannel-sendnotification.md) | "." |
| [IBidiRequest::GetEnumCount](..\bidispl\nf-bidispl-ibidirequest-getenumcount.md) | The GetEnumCount method gets the number of output results from the bidi request. |
| [IBidiRequest::GetOutputData](..\bidispl\nf-bidispl-ibidirequest-getoutputdata.md) | The GetOutputData method gets the specified output data coming back from the printer. |
| [IBidiRequest::GetResult](..\bidispl\nf-bidispl-ibidirequest-getresult.md) | The GetResult method tells whether the bidi request was successful. |
| [IBidiRequest::SetInputData](..\bidispl\nf-bidispl-ibidirequest-setinputdata.md) | The SetInputData method sets the data to send to the printer. |
| [IBidiRequest::SetSchema](..\bidispl\nf-bidispl-ibidirequest-setschema.md) | The SetSchema method sets the bidi schema string. |
| [IBidiRequestContainer::AddRequest](..\bidispl\nf-bidispl-ibidirequestcontainer-addrequest.md) | The AddRequest method adds a request to the request list. |
| [IBidiRequestContainer::GetEnumObject](..\bidispl\nf-bidispl-ibidirequestcontainer-getenumobject.md) | The GetEnumObject method enumerates the bidi requests in a list. |
| [IBidiRequestContainer::GetRequestCount](..\bidispl\nf-bidispl-ibidirequestcontainer-getrequestcount.md) | The GetRequestCount method gets the number of requests in the request list. |
| [IBidiSpl2::BindDevice](..\bidispl\nf-bidispl-ibidispl2-binddevice.md) | The BindDevice method binds a printer to a bidirectional printer communication (bidi communication) request. This method is similar to the OpenPrinter function. |
| [IBidiSpl2::SendRecvXMLStream](..\bidispl\nf-bidispl-ibidispl2-sendrecvxmlstream.md) | The SendRecvXMLStream method sends a bidirectional printer communication request and receives the response as IStream objects formatted in accordance with the Bidirectional Communication Schemas. |
| [IBidiSpl2::SendRecvXMLString](..\bidispl\nf-bidispl-ibidispl2-sendrecvxmlstring.md) | The SendRecvXMLString method sends a bidirectional printer communication request and receives the response as Unicode strings formatted in accordance with the Bidirectional Communication Schemas. |
| [IBidiSpl2::UnbindDevice](..\bidispl\nf-bidispl-ibidispl2-unbinddevice.md) | The UnbindDevice method releases a printer from a bidirectional printer communication (bidi communication) request. |
| [IBidiSpl::BindDevice](..\bidispl\nf-bidispl-ibidispl-binddevice.md) | The BindDevice method binds a printer to a bidi request. This method is similar to the OpenPrinter function. |
| [IBidiSpl::MultiSendRecv](..\bidispl\nf-bidispl-ibidispl-multisendrecv.md) | The MultiSendRecv method sends a list of bidi requests. |
| [IBidiSpl::SendRecv](..\bidispl\nf-bidispl-ibidispl-sendrecv.md) | The SendRecv method sends a bidi request to the printer. |
| [IBidiSpl::UnbindDevice](..\bidispl\nf-bidispl-ibidispl-unbinddevice.md) | The UnbindDevice method unbinds a printer from a bidi request. |
| [IFixedDocument::GetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixeddocument-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed document. |
| [IFixedDocument::GetUri](..\filterpipeline\nf-filterpipeline-ifixeddocument-geturi.md) | The GetUri method gets the URI of the fixed document. |
| [IFixedDocument::SetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixeddocument-setprintticket.md) | The SetPrintTicket method inserts a print ticket into the fixed document. |
| [IFixedDocumentSequence::GetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixeddocumentsequence-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed document sequence. |
| [IFixedDocumentSequence::GetUri](..\filterpipeline\nf-filterpipeline-ifixeddocumentsequence-geturi.md) | The GetUri method gets the URI of the fixed document sequence. |
| [IFixedDocumentSequence::SetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixeddocumentsequence-setprintticket.md) | The SetPrintTicket method inserts a print ticket into the fixed document sequence. |
| [IFixedPage::DeleteResource](..\filterpipeline\nf-filterpipeline-ifixedpage-deleteresource.md) | The DeleteResource method deletes a resource that is associated with the page. |
| [IFixedPage::GetPagePart](..\filterpipeline\nf-filterpipeline-ifixedpage-getpagepart.md) | The GetPagePart method gets the images, thumbnails, fonts, and so on in a page by using the URI. |
| [IFixedPage::GetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixedpage-getprintticket.md) | The GetPrintTicket method gets the print ticket object for the fixed page. |
| [IFixedPage::GetWriteStream](..\filterpipeline\nf-filterpipeline-ifixedpage-getwritestream.md) | The GetWriteStream method retrieves the stream object to write page markup to read . You can use this stream to change page markup. |
| [IFixedPage::GetXpsPartIterator](..\filterpipeline\nf-filterpipeline-ifixedpage-getxpspartiterator.md) | The GetXpsPartIterator method gets an iterator to enumerate all of the parts that are associated with the page. |
| [IFixedPage::SetPagePart](..\filterpipeline\nf-filterpipeline-ifixedpage-setpagepart.md) | The SetPagePart method associates a new part with the page. |
| [IFixedPage::SetPrintTicket](..\filterpipeline\nf-filterpipeline-ifixedpage-setprintticket.md) | The SetPrintTicket method associates a print ticket with the page. |
| [IInterFilterCommunicator::RequestReader](..\filterpipeline\nf-filterpipeline-iinterfiltercommunicator-requestreader.md) | The RequestReader method retrieves the reader interface for an IInterFilterCommunicator object. |
| [IInterFilterCommunicator::RequestWriter](..\filterpipeline\nf-filterpipeline-iinterfiltercommunicator-requestwriter.md) | The RequestWriter method retrieves the writer interface for an IInterFilterCommunicator object. |
| [IPartBase::GetPartCompression](..\filterpipeline\nf-filterpipeline-ipartbase-getpartcompression.md) | The GetPartCompression method gets the compression of the part. |
| [IPartBase::GetStream](..\filterpipeline\nf-filterpipeline-ipartbase-getstream.md) | The GetStream method gets the stream object that contains the part data. Each part has part-specific data that is associated with it (for example, a font, image, and page markup). |
| [IPartBase::GetUri](..\filterpipeline\nf-filterpipeline-ipartbase-geturi.md) | The GetUri method gets the URI of the part. |
| [IPartBase::SetPartCompression](..\filterpipeline\nf-filterpipeline-ipartbase-setpartcompression.md) | The SetPartCompression method sets the compression of the part. |
| [IPartDiscardControl::GetDiscardProperties](..\filterpipeline\nf-filterpipeline-ipartdiscardcontrol-getdiscardproperties.md) | The GetDiscardProperties method gets the properties of the discard control. |
| [IPartFont2::GetFontRestriction](..\filterpipeline\nf-filterpipeline-ipartfont2-getfontrestriction.md) | "." |
| [IPartFont::GetFontProperties](..\filterpipeline\nf-filterpipeline-ipartfont-getfontproperties.md) | The GetFontProperties method gets the font properties. |
| [IPartFont::SetFontContent](..\filterpipeline\nf-filterpipeline-ipartfont-setfontcontent.md) | The SetFontContent method sets the content of the font. |
| [IPartFont::SetFontOptions](..\filterpipeline\nf-filterpipeline-ipartfont-setfontoptions.md) | The SetFontOptions method sets the options for the font. |
| [IPartImage::GetImageProperties](..\filterpipeline\nf-filterpipeline-ipartimage-getimageproperties.md) | The GetImageProperties method gets an image property that is based on the content type. |
| [IPartImage::SetImageContent](..\filterpipeline\nf-filterpipeline-ipartimage-setimagecontent.md) | The SetImageContent method sets an image property that is based on the content type. |
| [IPartThumbnail::GetThumbnailProperties](..\filterpipeline\nf-filterpipeline-ipartthumbnail-getthumbnailproperties.md) | The GetThumbnailProperties method gets the thumbnail properties. |
| [IPartThumbnail::SetThumbnailContent](..\filterpipeline\nf-filterpipeline-ipartthumbnail-setthumbnailcontent.md) | The SetThumbnailContent method sets the thumbnail content for the part. |
| [IPrintAsyncCookie::CancelAsyncCall](..\prnasntp\nf-prnasntp-iprintasynccookie-cancelasynccall.md) | "." |
| [IPrintAsyncCookie::FinishAsyncCall](..\prnasntp\nf-prnasntp-iprintasynccookie-finishasynccall.md) | "." |
| [IPrintAsyncNewChannelCookie::FinishAsyncCallWithData](..\prnasntp\nf-prnasntp-iprintasyncnewchannelcookie-finishasynccallwithdata.md) | "." |
| [IPrintAsyncNotify::CreatePrintAsyncNotifyChannel](..\prnasntp\nf-prnasntp-iprintasyncnotify-createprintasyncnotifychannel.md) | "." |
| [IPrintAsyncNotify::CreatePrintAsyncNotifyRegistration](..\prnasntp\nf-prnasntp-iprintasyncnotify-createprintasyncnotifyregistration.md) | "." |
| [IPrintAsyncNotifyRegistration::RegisterForNotifications](..\prnasntp\nf-prnasntp-iprintasyncnotifyregistration-registerfornotifications.md) | "." |
| [IPrintAsyncNotifyRegistration::UnregisterForNotifications](..\prnasntp\nf-prnasntp-iprintasyncnotifyregistration-unregisterfornotifications.md) | "." |
| [IPrintAsyncNotifyServerReferral::AsyncGetServerReferral](..\prnasntp\nf-prnasntp-iprintasyncnotifyserverreferral-asyncgetserverreferral.md) | "." |
| [IPrintAsyncNotifyServerReferral::GetServerReferral](..\prnasntp\nf-prnasntp-iprintasyncnotifyserverreferral-getserverreferral.md) | "." |
| [IPrintAsyncNotifyServerReferral::SetServerReferral](..\prnasntp\nf-prnasntp-iprintasyncnotifyserverreferral-setserverreferral.md) | "." |
| [IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel](..\prnasntp\nf-prnasntp-iprintbidiasyncnotifyregistration-asyncgetnewchannel.md) | "." |
| [IPrintClassObjectFactory::GetPrintClassObject](..\filterpipeline\nf-filterpipeline-iprintclassobjectfactory-getprintclassobject.md) | The GetPrintClassObject method creates a print filter-related object for a specified printer by using the IID of the interface object to create. |
| [IPrintCoreHelper::CreateInstanceOfMSXMLObject](..\prcomoem\nf-prcomoem-iprintcorehelper-createinstanceofmsxmlobject.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::EnumConstrainedOptions](..\prcomoem\nf-prcomoem-iprintcorehelper-enumconstrainedoptions.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::EnumFeatures](..\prcomoem\nf-prcomoem-iprintcorehelper-enumfeatures.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::EnumOptions](..\prcomoem\nf-prcomoem-iprintcorehelper-enumoptions.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::GetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelper-getfontsubstitution.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::GetOption](..\prcomoem\nf-prcomoem-iprintcorehelper-getoption.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::SetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelper-setfontsubstitution.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::SetOptions](..\prcomoem\nf-prcomoem-iprintcorehelper-setoptions.md) | The IPrintCoreHelper |
| [IPrintCoreHelper::WhyConstrained](..\prcomoem\nf-prcomoem-iprintcorehelper-whyconstrained.md) | The IPrintCoreHelper |
| [IPrintCoreHelperPS::CreateInstanceOfMSXMLObject](..\prcomoem\nf-prcomoem-iprintcorehelperps-createinstanceofmsxmlobject.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::EnumConstrainedOptions](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumconstrainedoptions.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::EnumFeatures](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumfeatures.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::EnumOptions](..\prcomoem\nf-prcomoem-iprintcorehelperps-enumoptions.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::GetFeatureAttribute](..\prcomoem\nf-prcomoem-iprintcorehelperps-getfeatureattribute.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::GetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelperps-getfontsubstitution.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::GetGlobalAttribute](..\prcomoem\nf-prcomoem-iprintcorehelperps-getglobalattribute.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::GetOptionAttribute](..\prcomoem\nf-prcomoem-iprintcorehelperps-getoptionattribute.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::GetOption](..\prcomoem\nf-prcomoem-iprintcorehelperps-getoption.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::SetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelperps-setfontsubstitution.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::SetOptions](..\prcomoem\nf-prcomoem-iprintcorehelperps-setoptions.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperPS::WhyConstrained](..\prcomoem\nf-prcomoem-iprintcorehelperps-whyconstrained.md) | The IPrintCoreHelperPS |
| [IPrintCoreHelperUni2::GetNamedCommand](..\prcomoem\nf-prcomoem-iprintcorehelperuni2-getnamedcommand.md) | The GetNamedCommand method returns the specified command. |
| [IPrintCoreHelperUni::CreateDefaultGDLSnapshot](..\prcomoem\nf-prcomoem-iprintcorehelperuni-createdefaultgdlsnapshot.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::CreateGDLSnapshot](..\prcomoem\nf-prcomoem-iprintcorehelperuni-creategdlsnapshot.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::CreateInstanceOfMSXMLObject](..\prcomoem\nf-prcomoem-iprintcorehelperuni-createinstanceofmsxmlobject.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::EnumConstrainedOptions](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumconstrainedoptions.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::EnumFeatures](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumfeatures.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::EnumOptions](..\prcomoem\nf-prcomoem-iprintcorehelperuni-enumoptions.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::GetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelperuni-getfontsubstitution.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::GetOption](..\prcomoem\nf-prcomoem-iprintcorehelperuni-getoption.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::SetFontSubstitution](..\prcomoem\nf-prcomoem-iprintcorehelperuni-setfontsubstitution.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::SetOptions](..\prcomoem\nf-prcomoem-iprintcorehelperuni-setoptions.md) | The IPrintCoreHelperUni |
| [IPrintCoreHelperUni::WhyConstrained](..\prcomoem\nf-prcomoem-iprintcorehelperuni-whyconstrained.md) | The IPrintCoreHelperUni |
| [IPrintCorePS2::DrvWriteSpoolBuf](..\prcomoem\nf-prcomoem-iprintcoreps2-drvwritespoolbuf.md) | The IPrintCorePS2 |
| [IPrintCorePS2::EnumFeatures](..\prcomoem\nf-prcomoem-iprintcoreps2-enumfeatures.md) | The IPrintCorePS2 |
| [IPrintCorePS2::EnumOptions](..\prcomoem\nf-prcomoem-iprintcoreps2-enumoptions.md) | The IPrintCorePS2 |
| [IPrintCorePS2::GetFeatureAttribute](..\prcomoem\nf-prcomoem-iprintcoreps2-getfeatureattribute.md) | The IPrintCorePS2 |
| [IPrintCorePS2::GetGlobalAttribute](..\prcomoem\nf-prcomoem-iprintcoreps2-getglobalattribute.md) | The IPrintCorePS2 |
| [IPrintCorePS2::GetOptionAttribute](..\prcomoem\nf-prcomoem-iprintcoreps2-getoptionattribute.md) | The IPrintCorePS2 |
| [IPrintCorePS2::GetOptions](..\prcomoem\nf-prcomoem-iprintcoreps2-getoptions.md) | The IPrintCorePS2 |
| [IPrintCoreUI2::DrvGetDriverSetting](..\prcomoem\nf-prcomoem-iprintcoreui2-drvgetdriversetting.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::DrvUpdateUISetting](..\prcomoem\nf-prcomoem-iprintcoreui2-drvupdateuisetting.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::DrvUpgradeRegistrySetting](..\prcomoem\nf-prcomoem-iprintcoreui2-drvupgraderegistrysetting.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::EnumConstrainedOptions](..\prcomoem\nf-prcomoem-iprintcoreui2-enumconstrainedoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::EnumFeatures](..\prcomoem\nf-prcomoem-iprintcoreui2-enumfeatures.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::EnumOptions](..\prcomoem\nf-prcomoem-iprintcoreui2-enumoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::GetFeatureAttribute](..\prcomoem\nf-prcomoem-iprintcoreui2-getfeatureattribute.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::GetGlobalAttribute](..\prcomoem\nf-prcomoem-iprintcoreui2-getglobalattribute.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::GetOptionAttribute](..\prcomoem\nf-prcomoem-iprintcoreui2-getoptionattribute.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::GetOptions](..\prcomoem\nf-prcomoem-iprintcoreui2-getoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::QuerySimulationSupport](..\prcomoem\nf-prcomoem-iprintcoreui2-querysimulationsupport.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::SetOptions](..\prcomoem\nf-prcomoem-iprintcoreui2-setoptions.md) | The IPrintCoreUI2 |
| [IPrintCoreUI2::WhyConstrained](..\prcomoem\nf-prcomoem-iprintcoreui2-whyconstrained.md) | The IPrintCoreUI2 |
| [IPrintJob::RequestCancel](..\printerextension\nf-printerextension-iprintjob-requestcancel.md) | Requests the cancellation of a print job. |
| [IPrintJob::get_Id](..\printerextension\nf-printerextension-iprintjob-get_id.md) | Gets the print job identifier (ID). |
| [IPrintJob::get_Name](..\printerextension\nf-printerextension-iprintjob-get_name.md) | Gets the name of the print job. |
| [IPrintJob::get_PrintedPages](..\printerextension\nf-printerextension-iprintjob-get_printedpages.md) | Gets the number of pages that have been printed. |
| [IPrintJob::get_Status method](..\printerextension\nf-printerextension-iprintjob-get_status.md) | Gets the current status of the print job. |
| [IPrintJob::get_SubmissionTime](..\printerextension\nf-printerextension-iprintjob-get_submissiontime.md) | Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler). |
| [IPrintJob::get_TotalPages](..\printerextension\nf-printerextension-iprintjob-get_totalpages.md) | Gets the total number of pages that the document contains. |
| [IPrintJobCollection::GetAt](..\printerextension\nf-printerextension-iprintjobcollection-getat.md) | Gets a pointer to an IPrintJob object. |
| [IPrintJobCollection::get_Count](..\printerextension\nf-printerextension-iprintjobcollection-get_count.md) | Gets the number of jobs in the print queue. |
| [IPrintJobCollection::get__NewEnum](..\printerextension\nf-printerextension-iprintjobcollection-get__newenum.md) | Gets a pointer to the enumerants of IPrintJobCollection objects. |
| [IPrintOemDriverPS::DrvGetDriverSetting](..\prcomoem\nf-prcomoem-iprintoemdriverps-drvgetdriversetting.md) | The IPrintOemDriverPS |
| [IPrintOemDriverPS::DrvWriteSpoolBuf](..\prcomoem\nf-prcomoem-iprintoemdriverps-drvwritespoolbuf.md) | The IPrintOemDriverPS |
| [IPrintOemDriverUI::DrvGetDriverSetting](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvgetdriversetting.md) | The IPrintOemDriverUI |
| [IPrintOemDriverUI::DrvUpdateUISetting](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvupdateuisetting.md) | The IPrintOemDriverUI |
| [IPrintOemDriverUI::DrvUpgradeRegistrySetting](..\prcomoem\nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting.md) | The IPrintOemDriverUI |
| [IPrintOemDriverUni::DrvGetDriverSetting](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetdriversetting.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvGetGPDData](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetgpddata.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvGetStandardVariable](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvgetstandardvariable.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvUniTextOut](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvunitextout.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvWriteAbortBuf](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvwriteabortbuf.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvWriteSpoolBuf](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvwritespoolbuf.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvXMoveTo](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvxmoveto.md) | The IPrintOemDriverUni |
| [IPrintOemDriverUni::DrvYMoveTo](..\prcomoem\nf-prcomoem-iprintoemdriveruni-drvymoveto.md) | The IPrintOemDriverUni |
| [IPrintOemEngine::DisableDriver](..\prcomoem\nf-prcomoem-iprintoemengine-disabledriver.md) | "." |
| [IPrintOemEngine::DisablePDEV](..\prcomoem\nf-prcomoem-iprintoemengine-disablepdev.md) | "." |
| [IPrintOemEngine::EnableDriver](..\prcomoem\nf-prcomoem-iprintoemengine-enabledriver.md) | "." |
| [IPrintOemEngine::EnablePDEV](..\prcomoem\nf-prcomoem-iprintoemengine-enablepdev.md) | "." |
| [IPrintOemEngine::ResetPDEV](..\prcomoem\nf-prcomoem-iprintoemengine-resetpdev.md) | "." |
| [IPrintOemPS2::GetPDEVAdjustment](..\prcomoem\nf-prcomoem-iprintoemps2-getpdevadjustment.md) | The IPrintOemPS2 |
| [IPrintOemPS2::WritePrinter](..\prcomoem\nf-prcomoem-iprintoemps2-writeprinter.md) | The IPrintOemPS2 |
| [IPrintOemPS::Command](..\prcomoem\nf-prcomoem-iprintoemps-command.md) | The IPrintOemPS |
| [IPrintOemPS::DevMode](..\prcomoem\nf-prcomoem-iprintoemps-devmode.md) | The IPrintOemPS |
| [IPrintOemPS::DisableDriver](..\prcomoem\nf-prcomoem-iprintoemps-disabledriver.md) | The IPrintOemPS |
| [IPrintOemPS::DisablePDEV](..\prcomoem\nf-prcomoem-iprintoemps-disablepdev.md) | The IPrintOemPS |
| [IPrintOemPS::EnableDriver](..\prcomoem\nf-prcomoem-iprintoemps-enabledriver.md) | The IPrintOemPS |
| [IPrintOemPS::EnablePDEV](..\prcomoem\nf-prcomoem-iprintoemps-enablepdev.md) | The IPrintOemPS |
| [IPrintOemPS::GetInfo](..\prcomoem\nf-prcomoem-iprintoemps-getinfo.md) | A rendering plug-in's IPrintOemPS |
| [IPrintOemPS::PublishDriverInterface](..\prcomoem\nf-prcomoem-iprintoemps-publishdriverinterface.md) | The IPrintOemPS |
| [IPrintOemPS::ResetPDEV](..\prcomoem\nf-prcomoem-iprintoemps-resetpdev.md) | The IPrintOemPS |
| [IPrintOemPrintTicketProvider::BindPrinter](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-bindprinter.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::CompletePrintCapabilities](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-completeprintcapabilities.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-convertdevmodetoprintticket.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-convertprinttickettodevmode.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::ExpandIntentOptions](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-expandintentoptions.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::GetSupportedVersions](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-getsupportedversions.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::PublishPrintTicketHelperInterface](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-publishprinttickethelperinterface.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::QueryDeviceDefaultNamespace](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-querydevicedefaultnamespace.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemPrintTicketProvider::ValidatePrintTicket](..\prcomoem\nf-prcomoem-iprintoemprintticketprovider-validateprintticket.md) | The IPrintOemPrintTicketProvider |
| [IPrintOemUI2::DocumentEvent](..\prcomoem\nf-prcomoem-iprintoemui2-documentevent.md) | The IPrintOemUI2 |
| [IPrintOemUI2::HideStandardUI](..\prcomoem\nf-prcomoem-iprintoemui2-hidestandardui.md) | The IPrintOemUI2 |
| [IPrintOemUI2::QueryJobAttributes](..\prcomoem\nf-prcomoem-iprintoemui2-queryjobattributes.md) | The IPrintOemUI2 |
| [IPrintOemUI::CommonUIProp](..\prcomoem\nf-prcomoem-iprintoemui-commonuiprop.md) | The IPrintOemUI |
| [IPrintOemUI::DevMode](..\prcomoem\nf-prcomoem-iprintoemui-devmode.md) | The IPrintOemUI |
| [IPrintOemUI::DevQueryPrintEx](..\prcomoem\nf-prcomoem-iprintoemui-devqueryprintex.md) | The IPrintOemUI |
| [IPrintOemUI::DeviceCapabilities](..\prcomoem\nf-prcomoem-iprintoemui-devicecapabilities.md) | The IPrintOemUI |
| [IPrintOemUI::DevicePropertySheets](..\prcomoem\nf-prcomoem-iprintoemui-devicepropertysheets.md) | The IPrintOemUI |
| [IPrintOemUI::DocumentPropertySheets](..\prcomoem\nf-prcomoem-iprintoemui-documentpropertysheets.md) | The IPrintOemUI |
| [IPrintOemUI::DriverEvent](..\prcomoem\nf-prcomoem-iprintoemui-driverevent.md) | The printer driver's DrvDriverEvent function calls a user interface plug-in's IPrintOemUI |
| [IPrintOemUI::FontInstallerDlgProc](..\prcomoem\nf-prcomoem-iprintoemui-fontinstallerdlgproc.md) | A user interface plug-in's IPrintOemUI |
| [IPrintOemUI::GetInfo](..\prcomoem\nf-prcomoem-iprintoemui-getinfo.md) | A user interface plug-in's IPrintOemUI |
| [IPrintOemUI::PrinterEvent](..\prcomoem\nf-prcomoem-iprintoemui-printerevent.md) | The IPrintOemUI |
| [IPrintOemUI::PublishDriverInterface](..\prcomoem\nf-prcomoem-iprintoemui-publishdriverinterface.md) | The IPrintOemUI |
| [IPrintOemUI::QueryColorProfile](..\prcomoem\nf-prcomoem-iprintoemui-querycolorprofile.md) | The IPrintOemUI |
| [IPrintOemUI::UpdateExternalFonts](..\prcomoem\nf-prcomoem-iprintoemui-updateexternalfonts.md) | The IPrintOemUI |
| [IPrintOemUI::UpgradePrinter](..\prcomoem\nf-prcomoem-iprintoemui-upgradeprinter.md) | The IPrintOemUI |
| [IPrintOemUIMXDC::AdjustDPI](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustdpi.md) | The IPrintOemUIMXDC |
| [IPrintOemUIMXDC::AdjustImageCompression](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustimagecompression.md) | The IPrintOemUIMXDC |
| [IPrintOemUIMXDC::AdjustImageableArea](..\prcomoem\nf-prcomoem-iprintoemuimxdc-adjustimageablearea.md) | The IPrintOemUIMXDC |
| [IPrintOemUni2::GetImplementedMethod](..\prcomoem\nf-prcomoem-iprintoemuni2-getimplementedmethod.md) | The IPrintOemUni2 |
| [IPrintOemUni2::WritePrinter](..\prcomoem\nf-prcomoem-iprintoemuni2-writeprinter.md) | The IPrintOemUni2 |
| [IPrintOemUni3::DownloadPattern](..\prcomoem\nf-prcomoem-iprintoemuni3-downloadpattern.md) | The IPrintOemUni3 |
| [IPrintOemUni3::GetImplementedMethod](..\prcomoem\nf-prcomoem-iprintoemuni3-getimplementedmethod.md) | The IPrintOemUni3 |
| [IPrintOemUni3::GetPDEVAdjustment](..\prcomoem\nf-prcomoem-iprintoemuni3-getpdevadjustment.md) | The IPrintOemUni3 |
| [IPrintOemUni3::SetBandSize](..\prcomoem\nf-prcomoem-iprintoemuni3-setbandsize.md) | The IPrintOemUni3 |
| [IPrintOemUni::CommandCallback](..\prcomoem\nf-prcomoem-iprintoemuni-commandcallback.md) | The IPrintOemUni |
| [IPrintOemUni::Compression](..\prcomoem\nf-prcomoem-iprintoemuni-compression.md) | The IPrintOemUni |
| [IPrintOemUni::DevMode](..\prcomoem\nf-prcomoem-iprintoemuni-devmode.md) | The IPrintOemUni |
| [IPrintOemUni::DisableDriver](..\prcomoem\nf-prcomoem-iprintoemuni-disabledriver.md) | The IPrintOemuNI |
| [IPrintOemUni::DisablePDEV](..\prcomoem\nf-prcomoem-iprintoemuni-disablepdev.md) | The IPrintOemUni |
| [IPrintOemUni::DownloadCharGlyph](..\prcomoem\nf-prcomoem-iprintoemuni-downloadcharglyph.md) | The IPrintOemUni |
| [IPrintOemUni::DownloadFontHeader](..\prcomoem\nf-prcomoem-iprintoemuni-downloadfontheader.md) | The IPrintOemUni |
| [IPrintOemUni::DriverDMS](..\prcomoem\nf-prcomoem-iprintoemuni-driverdms.md) | The IPrintOemUni |
| [IPrintOemUni::EnableDriver](..\prcomoem\nf-prcomoem-iprintoemuni-enabledriver.md) | The IPrintOemUni |
| [IPrintOemUni::EnablePDEV](..\prcomoem\nf-prcomoem-iprintoemuni-enablepdev.md) | The IPrintOemUni |
| [IPrintOemUni::FilterGraphics](..\prcomoem\nf-prcomoem-iprintoemuni-filtergraphics.md) | The IPrintOemUni |
| [IPrintOemUni::GetImplementedMethod](..\prcomoem\nf-prcomoem-iprintoemuni-getimplementedmethod.md) | The IPrintOemUni |
| [IPrintOemUni::GetInfo](..\prcomoem\nf-prcomoem-iprintoemuni-getinfo.md) | A rendering plug-in's IPrintOemUni |
| [IPrintOemUni::HalftonePattern](..\prcomoem\nf-prcomoem-iprintoemuni-halftonepattern.md) | The IPrintOemUni |
| [IPrintOemUni::ImageProcessing](..\prcomoem\nf-prcomoem-iprintoemuni-imageprocessing.md) | The IPrintOemUni |
| [IPrintOemUni::MemoryUsage](..\prcomoem\nf-prcomoem-iprintoemuni-memoryusage.md) | The IPrintOemUni |
| [IPrintOemUni::OutputCharStr](..\prcomoem\nf-prcomoem-iprintoemuni-outputcharstr.md) | The IPrintOemUni |
| [IPrintOemUni::PublishDriverInterface](..\prcomoem\nf-prcomoem-iprintoemuni-publishdriverinterface.md) | The IPrintOemUni |
| [IPrintOemUni::ResetPDEV](..\prcomoem\nf-prcomoem-iprintoemuni-resetpdev.md) | The IPrintOemUni |
| [IPrintOemUni::SendFontCmd](..\prcomoem\nf-prcomoem-iprintoemuni-sendfontcmd.md) | The IPrintOemUni |
| [IPrintOemUni::TTDownloadMethod](..\prcomoem\nf-prcomoem-iprintoemuni-ttdownloadmethod.md) | The IPrintOemUni |
| [IPrintOemUni::TTYGetInfo](..\prcomoem\nf-prcomoem-iprintoemuni-ttygetinfo.md) | The IPrintOemUni |
| [IPrintOemUni::TextOutAsBitmap](..\prcomoem\nf-prcomoem-iprintoemuni-textoutasbitmap.md) | The IPrintOemUni |
| [IPrintPipelineFilter::InitializeFilter](..\filterpipeline\nf-filterpipeline-iprintpipelinefilter-initializefilter.md) | The InitializeFilter method initializes a filter. |
| [IPrintPipelineFilter::ShutdownOperation](..\filterpipeline\nf-filterpipeline-iprintpipelinefilter-shutdownoperation.md) | The Pipeline Manager uses the ShutdownOperation method to shut down a filter if the print job is canceled or an error occurs. |
| [IPrintPipelineFilter::StartOperation](..\filterpipeline\nf-filterpipeline-iprintpipelinefilter-startoperation.md) | The StartOperation method starts the operation of a filter. The filter reads, processes, and writes data in this method. |
| [IPrintPipelineManagerControl::FilterFinished](..\filterpipeline\nf-filterpipeline-iprintpipelinemanagercontrol-filterfinished.md) | The FilterFinished method reports that a filter is finished processing. |
| [IPrintPipelineManagerControl::RequestShutdown](..\filterpipeline\nf-filterpipeline-iprintpipelinemanagercontrol-requestshutdown.md) | The RequestShutdown method requests that a pipeline be shut down. |
| [IPrintPipelineProgressReport::ReportProgress](..\filterpipeline\nf-filterpipeline-iprintpipelineprogressreport-reportprogress.md) | The ReportProgress method reports the progress of the XPS job consumption to the pipeline manager. |
| [IPrintPipelinePropertyBag::AddProperty](..\filterpipeline\nf-filterpipeline-iprintpipelinepropertybag-addproperty.md) | The AddProperty method adds a property to a property bag. |
| [IPrintPipelinePropertyBag::DeleteProperty](..\filterpipeline\nf-filterpipeline-iprintpipelinepropertybag-deleteproperty.md) | The DeleteProperty method deletes a property from a property bag. |
| [IPrintPipelinePropertyBag::GetProperty](..\filterpipeline\nf-filterpipeline-iprintpipelinepropertybag-getproperty.md) | The GetProperty method gets a property from a property bag. |
| [IPrintReadStream::ReadBytes](..\filterpipeline\nf-filterpipeline-iprintreadstream-readbytes.md) | The ReadBytes method reads a number of bytes into a buffer. |
| [IPrintReadStream::Seek](..\filterpipeline\nf-filterpipeline-iprintreadstream-seek.md) | The Seek method changes the seek pointer to a new location in the stream. |
| [IPrintReadStreamFactory::GetStream](..\filterpipeline\nf-filterpipeline-iprintreadstreamfactory-getstream.md) | The GetStream method gets the stream interface. |
| [IPrintSchemaAsyncOperation::Cancel](..\printerextension\nf-printerextension-iprintschemaasyncoperation-cancel.md) | Cancels the asynchronous PrintSchema operation. |
| [IPrintSchemaAsyncOperation::Start](..\printerextension\nf-printerextension-iprintschemaasyncoperation-start.md) | Starts the asynchronous PrintSchema operation. |
| [IPrintSchemaAsyncOperationEvent::Completed](..\printerextension\nf-printerextension-iprintschemaasyncoperationevent-completed.md) | Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed. |
| [IPrintSchemaCapabilities2::GetParameterDefinition](..\printerextension\nf-printerextension-iprintschemacapabilities2-getparameterdefinition.md) | The GetParameterDefinition method retrieves the IPrintSchemaParameterDefinition object, and it represents the &lt;psf |
| [IPrintSchemaCapabilities::GetFeatureByKeyName](..\printerextension\nf-printerextension-iprintschemacapabilities-getfeaturebykeyname.md) | Gets a feature from the PrintCapabilities based on a given key name. |
| [IPrintSchemaCapabilities::GetFeature](..\printerextension\nf-printerextension-iprintschemacapabilities-getfeature.md) | Gets a named feature from the PrintCapabilities, by name and full namespace URI. |
| [IPrintSchemaCapabilities::GetOptions](..\printerextension\nf-printerextension-iprintschemacapabilities-getoptions.md) | Gets all the options of a feature. |
| [IPrintSchemaCapabilities::GetSelectedOptionInPrintTicket](..\printerextension\nf-printerextension-iprintschemacapabilities-getselectedoptioninprintticket.md) | Gets the selected option for a feature in IPrintSchemaTicket. |
| [IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue](..\printerextension\nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsmaxvalue.md) | Gets the JobCopiesAllDocuments parameter maximum value. |
| [IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue](..\printerextension\nf-printerextension-iprintschemacapabilities-get_jobcopiesalldocumentsminvalue.md) | Gets the JobCopiesAllDocuments parameter minimum value. |
| [IPrintSchemaCapabilities::get_PageImageableSize](..\printerextension\nf-printerextension-iprintschemacapabilities-get_pageimageablesize.md) | Gets the imageable area information of the printer. |
| [IPrintSchemaDisplayableElement::get_DisplayName](..\printerextension\nf-printerextension-iprintschemadisplayableelement-get_displayname.md) | Gets a displayable string for this item. |
| [IPrintSchemaElement::get_Name](..\printerextension\nf-printerextension-iprintschemaelement-get_name.md) | Gets the base value of the &#0034;name&#0034; attribute of this node. |
| [IPrintSchemaElement::get_NamespaceUri](..\printerextension\nf-printerextension-iprintschemaelement-get_namespaceuri.md) | Gets the namespace URI value of the &#0034;name&#0034; attribute of this node. |
| [IPrintSchemaElement::get_XmlNode](..\printerextension\nf-printerextension-iprintschemaelement-get_xmlnode.md) | Gets the IXMLDOMNode object associated with this item. |
| [IPrintSchemaFeature::GetOption](..\printerextension\nf-printerextension-iprintschemafeature-getoption.md) | Gets the option with the given name. |
| [IPrintSchemaFeature::get_DisplayUI](..\printerextension\nf-printerextension-iprintschemafeature-get_displayui.md) | Gets the setting that indicates whether or not to show the print UI. |
| [IPrintSchemaFeature::get_SelectedOption](..\printerextension\nf-printerextension-iprintschemafeature-get_selectedoption.md) | Gets an IPrintSchemaOption representing the selected option. |
| [IPrintSchemaFeature::get_SelectionType](..\printerextension\nf-printerextension-iprintschemafeature-get_selectiontype.md) | Gets the selection type of the Feature. |
| [IPrintSchemaFeature::put_SelectedOption](..\printerextension\nf-printerextension-iprintschemafeature-put_selectedoption.md) | Changes the selected option of the Print Schema Feature element to the specified IPrintSchemaOption element. |
| [IPrintSchemaNUpOption::get_PagesPerSheet](..\printerextension\nf-printerextension-iprintschemanupoption-get_pagespersheet.md) | Gets the number of pages per sheet. |
| [IPrintSchemaOption::GetPropertyValue](..\printerextension\nf-printerextension-iprintschemaoption-getpropertyvalue.md) | Gets the XML node for the &#0034;value&#0034; child element of a &#0034;Property&#0034; or a &#0034;ScoredProperty&#0034; element with the given name. |
| [IPrintSchemaOption::get_Constrained](..\printerextension\nf-printerextension-iprintschemaoption-get_constrained.md) | Gets the constraint setting type for the schema option. |
| [IPrintSchemaOption::get_Selected](..\printerextension\nf-printerextension-iprintschemaoption-get_selected.md) | Indicates whether this option is selected. |
| [IPrintSchemaOptionCollection::GetAt](..\printerextension\nf-printerextension-iprintschemaoptioncollection-getat.md) | Gets a pointer to an IPrintSchemaOption object. |
| [IPrintSchemaOptionCollection::get_Count](..\printerextension\nf-printerextension-iprintschemaoptioncollection-get_count.md) | Gets a count of the number of IPrintSchemaOption objects in the collection. |
| [IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_extentheightinmicrons.md) | Gets the vertical distance between the origin and the bounding limit of the canvas application media size. |
| [IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_extentwidthinmicrons.md) | Gets the horizontal distance between the origin and the bounding limit of the application media size. |
| [IPrintSchemaPageImageableSize::get_ImageableSizeHeightInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_imageablesizeheightinmicrons.md) | Gets the vertical dimension of the application media size relative to the page orientation. |
| [IPrintSchemaPageImageableSize::get_ImageableSizeWidthInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_imageablesizewidthinmicrons.md) | Gets the horizontal dimension of the application media size relative to the page orientation. |
| [IPrintSchemaPageImageableSize::get_OriginHeightInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_originheightinmicrons.md) | Gets the vertical origin of the imageable area relative to the application media size. |
| [IPrintSchemaPageImageableSize::get_OriginWidthInMicrons](..\printerextension\nf-printerextension-iprintschemapageimageablesize-get_originwidthinmicrons.md) | Gets the horizontal origin of the imageable area relative to the application media size. |
| [IPrintSchemaPageMediaSizeOption::get_HeightInMicrons](..\printerextension\nf-printerextension-iprintschemapagemediasizeoption-get_heightinmicrons.md) | Gets the height of the page in microns. |
| [IPrintSchemaPageMediaSizeOption::get_WidthInMicrons](..\printerextension\nf-printerextension-iprintschemapagemediasizeoption-get_widthinmicrons.md) | Gets the width of the page in microns. |
| [IPrintSchemaParameterDefinition::get_DataType](..\printerextension\nf-printerextension-iprintschemaparameterdefinition-get_datatype.md) | The DataType property gets the PrintSchemaParameterDataType enumerated value that indicates the expected data type for the Print Schema parameter. |
| [IPrintSchemaParameterDefinition::get_RangeMax](..\printerextension\nf-printerextension-iprintschemaparameterdefinition-get_rangemax.md) | The RangeMax property gets the maximum value of the allowed data range. |
| [IPrintSchemaParameterDefinition::get_RangeMin](..\printerextension\nf-printerextension-iprintschemaparameterdefinition-get_rangemin.md) | The RangeMin property gets the minimum value of the allowed data range. |
| [IPrintSchemaParameterDefinition::get_UnitType](..\printerextension\nf-printerextension-iprintschemaparameterdefinition-get_unittype.md) | The UnitType property gets the unit type. |
| [IPrintSchemaParameterDefinition::get_UserInputRequired](..\printerextension\nf-printerextension-iprintschemaparameterdefinition-get_userinputrequired.md) | The UserInputRequired property gets the Boolean value that indicates whether or not a user input value is required for the Print Schema parameter. |
| [IPrintSchemaParameterInitializer::get_Value](..\printerextension\nf-printerextension-iprintschemaparameterinitializer-get_value.md) | The Value (get_Value) property gets the current value of the IPrintSchemaParameterInitializer object. |
| [IPrintSchemaParameterInitializer::put_Value](..\printerextension\nf-printerextension-iprintschemaparameterinitializer-put_value.md) | The Value (put_Value) property modifies the value of the IPrintSchemaParameterInitializer object. |
| [IPrintSchemaTicket2::GetParameterInitializer](..\printerextension\nf-printerextension-iprintschematicket2-getparameterinitializer.md) | The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the &lt;psf |
| [IPrintSchemaTicket::CommitAsync](..\printerextension\nf-printerextension-iprintschematicket-commitasync.md) | Gets an asynchronous PrintTicket commit operation context. |
| [IPrintSchemaTicket::GetCapabilities](..\printerextension\nf-printerextension-iprintschematicket-getcapabilities.md) | Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object. |
| [IPrintSchemaTicket::GetFeatureByKeyName](..\printerextension\nf-printerextension-iprintschematicket-getfeaturebykeyname.md) | Gets a feature from the PrintTicket based on the specified key name. |
| [IPrintSchemaTicket::GetFeature](..\printerextension\nf-printerextension-iprintschematicket-getfeature.md) | Gets a named feature from the PrintTicket, by name and full namespace URI. |
| [IPrintSchemaTicket::NotifyXmlChanged](..\printerextension\nf-printerextension-iprintschematicket-notifyxmlchanged.md) | Notifies the print system that the XML DOM object has changed. |
| [IPrintSchemaTicket::ValidateAsync](..\printerextension\nf-printerextension-iprintschematicket-validateasync.md) | Gets an asynchronous PrintTicket validation operation context. |
| [IPrintSchemaTicket::get_JobCopiesAllDocuments](..\printerextension\nf-printerextension-iprintschematicket-get_jobcopiesalldocuments.md) | Gets the copy count. |
| [IPrintSchemaTicket::put_JobCopiesAllDocuments](..\printerextension\nf-printerextension-iprintschematicket-put_jobcopiesalldocuments.md) | Sets the copy count. |
| [IPrintUnidiAsyncNotifyRegistration::AsyncGetNotification](..\prnasntp\nf-prnasntp-iprintunidiasyncnotifyregistration-asyncgetnotification.md) | "." |
| [IPrintWriteStream::Close](..\filterpipeline\nf-filterpipeline-iprintwritestream-close.md) | The Close method closes a stream and ends the writing to that stream. This method is mandatory. You must call this method when the filter is done writing. |
| [IPrintWriteStream::WriteBytes](..\filterpipeline\nf-filterpipeline-iprintwritestream-writebytes.md) | The WriteBytes method writes a specified number of bytes to a stream. |
| [IPrintWriteStreamFlush::FlushData](..\filterpipeline\nf-filterpipeline-iprintwritestreamflush-flushdata.md) | The FlushData method flushes buffered data to a data stream while leaving the stream open, allowing the caller to write additional data to the stream. |
| [IPrinterBidiSetRequestCallback::Completed](..\printerextension\nf-printerextension-iprinterbidisetrequestcallback-completed.md) | Invoked when the Bidi “Set”” operation is completed. |
| [IPrinterExtensionAsyncOperation::Cancel](..\printerextension\nf-printerextension-iprinterextensionasyncoperation-cancel.md) | Cancels the asynchronous operation. |
| [IPrinterExtensionContext::get_DriverProperties](..\printerextension\nf-printerextension-iprinterextensioncontext-get_driverproperties.md) | Gets the driver property bag. |
| [IPrinterExtensionContext::get_PrintSchemaTicket](..\printerextension\nf-printerextension-iprinterextensioncontext-get_printschematicket.md) | Gets the print ticket that is appropriate for the queue and the activation. |
| [IPrinterExtensionContext::get_PrinterQueue](..\printerextension\nf-printerextension-iprinterextensioncontext-get_printerqueue.md) | Gets the queue for the printer. |
| [IPrinterExtensionContext::get_UserProperties](..\printerextension\nf-printerextension-iprinterextensioncontext-get_userproperties.md) | Gets the user property bag for this app. |
| [IPrinterExtensionContextCollection::GetAt](..\printerextension\nf-printerextension-iprinterextensioncontextcollection-getat.md) | Gets a pointer to an IPrinterExtensionContext object. |
| [IPrinterExtensionContextCollection::get_Count](..\printerextension\nf-printerextension-iprinterextensioncontextcollection-get_count.md) | Gets a count of the number of IPrinterExtensionContext objects in the collection. |
| [IPrinterExtensionContextCollection::get__NewEnum method](..\printerextension\nf-printerextension-iprinterextensioncontextcollection-get__newenum.md) | Gets a pointer to the enumerants of IPrinterExtensionContextCollection objects. |
| [IPrinterExtensionEvent::OnDriverEvent](..\printerextension\nf-printerextension-iprinterextensionevent-ondriverevent.md) | Called when a driver event occurs. |
| [IPrinterExtensionEvent::OnPrinterQueuesEnumerated](..\printerextension\nf-printerextension-iprinterextensionevent-onprinterqueuesenumerated.md) | Called when printer queues are enumerated. |
| [IPrinterExtensionEventArgs::get_BidiNotification](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_bidinotification.md) | Gets the text of the bidirectional communication (Bidi) notification, if applicable. |
| [IPrinterExtensionEventArgs::get_DetailedReasonId](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_detailedreasonid.md) | Gets a more detailed activation reason than what can be retrieved from ReasonId. |
| [IPrinterExtensionEventArgs::get_ReasonId](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_reasonid.md) | Gets the reason why the printer extension was activated. |
| [IPrinterExtensionEventArgs::get_Request](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_request.md) | Gets the IPrinterExtensionRequest object for the current event. |
| [IPrinterExtensionEventArgs::get_SourceApplication](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_sourceapplication.md) | Gets the name of the application that invoked the printer extension. |
| [IPrinterExtensionEventArgs::get_WindowModal](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_windowmodal.md) | Gets the run mode parameter that determines whether or not the printer extension should be run as modal. |
| [IPrinterExtensionEventArgs::get_WindowParent](..\printerextension\nf-printerextension-iprinterextensioneventargs-get_windowparent.md) | Gets the handle of the parent window. |
| [IPrinterExtensionManager::DisableEvents](..\printerextension\nf-printerextension-iprinterextensionmanager-disableevents.md) | Disallows events to be generated. |
| [IPrinterExtensionManager::EnableEvents](..\printerextension\nf-printerextension-iprinterextensionmanager-enableevents.md) | The EnableEvents method allows events to be generated for the specified printer driver until DisableEvents is called. |
| [IPrinterExtensionRequest::Cancel](..\printerextension\nf-printerextension-iprinterextensionrequest-cancel.md) | Completes the extension event with a cancellation. |
| [IPrinterExtensionRequest::Complete](..\printerextension\nf-printerextension-iprinterextensionrequest-complete.md) | Completes the extension event. |
| [IPrinterPropertyBag::GetBool](..\printerextension\nf-printerextension-iprinterpropertybag-getbool.md) | Reads a specified boolean property. |
| [IPrinterPropertyBag::GetBytes](..\printerextension\nf-printerextension-iprinterpropertybag-getbytes.md) | Reads a byte array property. |
| [IPrinterPropertyBag::GetInt32](..\printerextension\nf-printerextension-iprinterpropertybag-getint32.md) | Reads an integer property. |
| [IPrinterPropertyBag::GetReadStream](..\printerextension\nf-printerextension-iprinterpropertybag-getreadstream.md) | Gets a stream in order to read from a stream property. |
| [IPrinterPropertyBag::GetString](..\printerextension\nf-printerextension-iprinterpropertybag-getstring.md) | Reads a string property. |
| [IPrinterPropertyBag::GetWriteStream](..\printerextension\nf-printerextension-iprinterpropertybag-getwritestream.md) | Gets a stream in order to write a stream property. |
| [IPrinterPropertyBag::SetBool](..\printerextension\nf-printerextension-iprinterpropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterPropertyBag::SetBytes](..\printerextension\nf-printerextension-iprinterpropertybag-setbytes.md) | Writes a byte array property. |
| [IPrinterPropertyBag::SetInt32](..\printerextension\nf-printerextension-iprinterpropertybag-setint32.md) | Writes an integer property. |
| [IPrinterPropertyBag::SetString](..\printerextension\nf-printerextension-iprinterpropertybag-setstring.md) | Writes a string property. |
| [IPrinterQueue2::GetPrinterQueueView](..\printerextension\nf-printerextension-iprinterqueue2-getprinterqueueview.md) | Retrieves an IPrinterQueueView object, and initializes the object with the range of jobs to be monitored. |
| [IPrinterQueue2::SendBidiSetRequestAsync](..\printerextension\nf-printerextension-iprinterqueue2-sendbidisetrequestasync.md) | Uses an XML string value to send a Bidi Set request as an asynchronous operation. |
| [IPrinterQueue::GetProperties](..\printerextension\nf-printerextension-iprinterqueue-getproperties.md) | Gets the properties in the property bag for the queue. |
| [IPrinterQueue::SendBidiQuery](..\printerextension\nf-printerextension-iprinterqueue-sendbidiquery.md) | Performs an asynchronous refresh operation with the specified query, and invokes the IPrinterQueueEvent |
| [IPrinterQueue::get_Handle](..\printerextension\nf-printerextension-iprinterqueue-get_handle.md) | Gets the underlying native handle for this print queue. |
| [IPrinterQueue::get_Name](..\printerextension\nf-printerextension-iprinterqueue-get_name.md) | Gets the name of the printer for this print queue. |
| [IPrinterQueueEvent::OnBidiResponseReceived](..\printerextension\nf-printerextension-iprinterqueueevent-onbidiresponsereceived.md) | Called when a bidi response is received. |
| [IPrinterQueueView::SetViewRange](..\printerextension\nf-printerextension-iprinterqueueview-setviewrange.md) | Sets the range of print jobs being monitored. |
| [IPrinterQueueViewEvent::OnChanged](..\printerextension\nf-printerextension-iprinterqueueviewevent-onchanged.md) | Provides an IPrintJobCollection object that provides a snapshot of a range of print jobs in the queue. |
| [IPrinterScriptContext::get_DriverProperties](..\printerextension\nf-printerextension-iprinterscriptcontext-get_driverproperties.md) | Provides access to the driver property bag, if the property bag is present. |
| [IPrinterScriptContext::get_QueueProperties](..\printerextension\nf-printerextension-iprinterscriptcontext-get_queueproperties.md) | Provides access to the queue property bag, if the property bag is present. |
| [IPrinterScriptContext::get_UserProperties](..\printerextension\nf-printerextension-iprinterscriptcontext-get_userproperties.md) | Provides access to the user property bag, if the property bag is present. |
| [IPrinterScriptablePropertyBag2::GetReadStreamAsXML](..\printerextension\nf-printerextension-iprinterscriptablepropertybag2-getreadstreamasxml.md) | "." |
| [IPrinterScriptablePropertyBag::GetBool](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getbool.md) | Gets a specified boolean property. |
| [IPrinterScriptablePropertyBag::GetBytes](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getbytes.md) | Gets a byte array property. |
| [IPrinterScriptablePropertyBag::GetInt32](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getint32.md) | Gets an integer property. |
| [IPrinterScriptablePropertyBag::GetReadStream](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getreadstream.md) | Gets a read stream and uses it to read from a property. |
| [IPrinterScriptablePropertyBag::GetString](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getstring.md) | Gets a string property. |
| [IPrinterScriptablePropertyBag::GetWriteStream](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-getwritestream.md) | Gets a stream and uses it to write to a stream property. |
| [IPrinterScriptablePropertyBag::SetBool](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setbool.md) | Writes a specified boolean property value. |
| [IPrinterScriptablePropertyBag::SetBytes](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setbytes.md) | Writes a byte array property. |
| [IPrinterScriptablePropertyBag::SetInt32](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setint32.md) | Writes an integer property. |
| [IPrinterScriptablePropertyBag::SetString](..\printerextension\nf-printerextension-iprinterscriptablepropertybag-setstring.md) | Writes a string property. |
| [IPrinterScriptableSequentialStream::Read](..\printerextension\nf-printerextension-iprinterscriptablesequentialstream-read.md) | The Read method reads bytes from the stream and returns them as a JavaScript array. |
| [IPrinterScriptableSequentialStream::Write](..\printerextension\nf-printerextension-iprinterscriptablesequentialstream-write.md) | The Write method writes the provided JavaScript array to the stream and returns the number of bytes written. |
| [IPrinterScriptableStream::Commit](..\printerextension\nf-printerextension-iprinterscriptablestream-commit.md) | Commits the operation. |
| [IPrinterScriptableStream::Seek](..\printerextension\nf-printerextension-iprinterscriptablestream-seek.md) | Sets the seek pointer. |
| [IPrinterScriptableStream::SetSize](..\printerextension\nf-printerextension-iprinterscriptablestream-setsize.md) | Sets the size of the scriptable stream, in bytes. |
| [IXpsDocument::GetThumbnail](..\filterpipeline\nf-filterpipeline-ixpsdocument-getthumbnail.md) | The GetThumbnail method gets the document thumbnail object. |
| [IXpsDocument::SetThumbnail](..\filterpipeline\nf-filterpipeline-ixpsdocument-setthumbnail.md) | The SetThumbnail method removes the current thumbnail object from the document and inserts a new one. |
| [IXpsDocumentConsumer::CloseSender](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-closesender.md) | The CloseSender method tells the Pipeline Manager that the filter is done sending XPS parts. |
| [IXpsDocumentConsumer::GetNewEmptyPart](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-getnewemptypart.md) | The GetNewEmptyPart method creates a new XPS part. |
| [IXpsDocumentConsumer::SendFixedDocumentSequence](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocumentsequence.md) | The SendFixedDocumentSequence method sends a fixed document sequence to the pipeline. |
| [IXpsDocumentConsumer::SendFixedDocument](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-sendfixeddocument.md) | The SendFixedDocument method sends a fixed document object to the pipeline. |
| [IXpsDocumentConsumer::SendFixedPage](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-sendfixedpage.md) | The SendFixedPage method sends a fixed page of an XPS document to the pipeline. |
| [IXpsDocumentConsumer::SendXpsDocument](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-sendxpsdocument.md) | The SendXpsDocument method sends an XPS document to the pipeline. |
| [IXpsDocumentConsumer::SendXpsUnknown](..\filterpipeline\nf-filterpipeline-ixpsdocumentconsumer-sendxpsunknown.md) | The SendXpsUnknown method sends an XPS document part that cannot be identified to the filter pipeline. |
| [IXpsDocumentProvider::GetXpsPart](..\filterpipeline\nf-filterpipeline-ixpsdocumentprovider-getxpspart.md) | The GetXpsPart method retrieves several objects that make up an XPS document. |
| [IXpsPartIterator::Current](..\filterpipeline\nf-filterpipeline-ixpspartiterator-current.md) | The Current method provides the current URI and part. |
| [IXpsPartIterator::IsDone](..\filterpipeline\nf-filterpipeline-ixpspartiterator-isdone.md) | The IsDone method determines whether the iterator has finished the iteration. |
| [IXpsPartIterator::Next](..\filterpipeline\nf-filterpipeline-ixpspartiterator-next.md) | The Next method advances the iterator to the next part. |
| [IXpsPartIterator::Reset](..\filterpipeline\nf-filterpipeline-ixpspartiterator-reset.md) | The Reset method sets the iterator to the first element. |
| [IXpsRasterizationFactory1::CreateRasterizer](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizationfactory1-createrasterizer.md) | The CreateRasterize method creates an XPS rasterizer object that can handle high precision colors. |
| [IXpsRasterizationFactory2::CreateRasterizer](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizationfactory2-createrasterizer.md) | The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs. |
| [IXpsRasterizationFactory::CreateRasterizer](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizationfactory-createrasterizer.md) | The CreateRasterize method creates an XPS rasterizer object. |
| [IXpsRasterizer::RasterizeRect](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizer-rasterizerect.md) | The RasterizeRect method rasterizes an axis-aligned, rectangular region of an XPS fixed page. |
| [IXpsRasterizer::SetMinimalLineWidth](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizer-setminimallinewidth.md) | The SetMinimalLineWidth method allows the caller to set the minimum thickness (in pixels) of the lines that the device can render. |
| [IXpsRasterizerNotificationCallback::Continue](..\xpsrassvc\nf-xpsrassvc-ixpsrasterizernotificationcallback-continue.md) | The Continue method tells the caller (the XPS rasterization service) whether to continue rasterizing the current XPS fixed page. |

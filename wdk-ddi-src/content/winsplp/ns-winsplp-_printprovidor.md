---
UID: NS:winsplp._PRINTPROVIDOR
title: _PRINTPROVIDOR (winsplp.h)
description: The PRINTPROVIDOR structure is used as a parameter to a print provider's InitializePrintProvidor function.
old-location: print\printprovidor.htm
tech.root: print
ms.date: 04/03/2019
keywords: ["PRINTPROVIDOR structure"]
ms.keywords: "*LPPRINTPROVIDOR, LPPRINTPROVIDOR, LPPRINTPROVIDOR structure pointer [Print Devices], PRINTPROVIDOR, PRINTPROVIDOR structure [Print Devices], _PRINTPROVIDOR, print.printprovidor, spoolfnc_4fb8242e-e0a0-47e5-b01f-2a20932d4d84.xml, winsplp/LPPRINTPROVIDOR, winsplp/PRINTPROVIDOR"
ms.custom: RS5, 19H1
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: PRINTPROVIDOR, *LPPRINTPROVIDOR
f1_keywords:
 - _PRINTPROVIDOR
 - winsplp/_PRINTPROVIDOR
 - LPPRINTPROVIDOR
 - winsplp/LPPRINTPROVIDOR
 - PRINTPROVIDOR
 - winsplp/PRINTPROVIDOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsplp.h
api_name:
 - _PRINTPROVIDOR
 - LPPRINTPROVIDOR
 - PRINTPROVIDOR
---

# _PRINTPROVIDOR structure


## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

The PRINTPROVIDOR structure is used as a parameter to a print provider's [InitializePrintProvidor](./nf-winsplp-initializeprintprovidor.md) function. All structure member values are supplied by the provider.

## -struct-fields

### -field fpOpenPrinter

(Required.) Pointer to the provider's [OpenPrinter](/windows/win32/printdocs/openprinter) function. However, at the provider level, this function must supply one of the DWORD return values listed in the following table.

| Return value | Definition |
| --- | --- |
| ROUTER_SUCCESS | The provider supports the specified printer and has opened it. |
| ROUTER_STOP_ROUTING | The provider supports the specified printer, but an error occurred and the printer could not be opened. It is assumed that no other provider can support the printer. The function must call [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror). |
| ROUTER_UNKNOWN | The provider does not support the specified printer. The function must call [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) and specify ERROR_INVALID_NAME. |

The router calls each provider until one of them returns ROUTER_SUCCESS or ROUTER_STOP_ROUTING. If the provider returns ROUTER_SUCCESS, it must also return a unique handle. For more information, see [Introduction to Print Providers](/windows-hardware/drivers/print/introduction-to-print-providers).) The router first attempts to call the provider's **OpenPrinterEx** function. If that function is not supported, the router calls [OpenPrinter](/windows/win32/printdocs/openprinter).

### -field fpSetJob

(Required.) Pointer to the provider's [SetJob](/windows/win32/printdocs/setjob) function.

### -field fpGetJob

(Required.) Pointer to the provider's [GetJob](/windows/win32/printdocs/getjob) function.

### -field fpEnumJobs

(Required.) Pointer to the provider's [EnumJobs](/windows/win32/printdocs/enumjobs) function.

### -field fpAddPrinter

(Optional. Can be NULL.) Pointer to the provider's [AddPrinter](/windows/win32/printdocs/addprinter) function.

### -field fpDeletePrinter

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinter](/windows/win32/printdocs/deleteprinter) function.

### -field fpSetPrinter

(Required.) Pointer to the provider's [SetPrinter](/windows/win32/printdocs/setprinter) function.

### -field fpGetPrinter

(Required.) Pointer to the provider's [GetPrinter](/windows/win32/printdocs/getprinter) function. If you are [writing a network print provider](/windows-hardware/drivers/print/writing-a-network-print-provider) and **GetPrinter** is returning a [PRINTER_INFO_2](/windows/win32/printdocs/printer-info-2) structure, the function should supply only the **cJobs** and **Status** structure members. The [local print provider](/windows-hardware/drivers/print/local-print-provider)) supplies the rest of the structure members.

### -field fpEnumPrinters

(Required.) Pointer to the provider's [EnumPrinters](/windows/win32/printdocs/enumprinters) function.

### -field fpAddPrinterDriver

(Optional. Can be NULL.) Pointer to the provider's [AddPrinterDriver](/windows/win32/printdocs/addprinterdriver) function. If the provider does not support the specified driver or server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpEnumPrinterDrivers

(Optional. Can be NULL.) Pointer to the provider's [EnumPrinterDrivers](/windows/win32/printdocs/enumprinterdrivers) function. If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpGetPrinterDriver

(Optional. Can be NULL.) Pointer to the provider's [GetPrinterDriver](/windows/win32/printdocs/getprinterdriver) function. The router first attempts to call the provider's **GetPrinterDriverEx** function. If that function is not supported, the router calls **GetPrinterDriver**.

### -field fpGetPrinterDriverDirectory

(Optional. Can be NULL.) Pointer to the provider's [GetPrinterDriverDirectory](/windows/win32/printdocs/getprinterdriverdirectory) function. If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpDeletePrinterDriver

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterDriver](/windows/win32/printdocs/deleteprinterdriver) function. If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpAddPrintProcessor

(Optional. Can be NULL.) Pointer to the provider's [AddPrintProcessor](/windows/win32/printdocs/addprintprocessor) function.

### -field fpEnumPrintProcessors

(Optional. Can be NULL.) Pointer to the provider's [EnumPrintProcessors](/windows/win32/printdocs/enumprintprocessors) function.

### -field fpGetPrintProcessorDirectory

(Optional. Can be NULL.) Pointer to the provider's [GetPrintProcessorDirectory](/windows/win32/printdocs/getprintprocessordirectory) function.

### -field fpDeletePrintProcessor

(Optional. Can be NULL.) Pointer to the provider's [DeletePrintProcessor](/windows/win32/printdocs/deleteprintprocessor) function.

### -field fpEnumPrintProcessorDatatypes

(Optional. Can be NULL.) Pointer to the provider's [EnumPrintProcessorDatatypes](/windows/win32/printdocs/enumprintprocessordatatypes) function.

### -field fpStartDocPrinter

(Required.) Pointer to the provider's [StartDocPrinter](/windows/win32/printdocs/startdocprinter) function.

### -field fpStartPagePrinter

(Optional. Can be NULL.) Pointer to the provider's [StartPagePrinter](/windows/win32/printdocs/startpageprinter) function.

### -field fpWritePrinter

(Required.) Pointer to the provider's [WritePrinter](/windows/win32/printdocs/writeprinter) function.

### -field fpEndPagePrinter

(Optional. Can be NULL.) Pointer to the provider's [EndPagePrinter](/windows/win32/printdocs/endpageprinter)function.

### -field fpAbortPrinter

(Required.) Pointer to the provider's [AbortPrinter](/windows/win32/printdocs/abortprinter) function.

### -field fpReadPrinter

(Optional. Can be NULL.) Pointer to the provider's [ReadPrinter](/windows/win32/printdocs/readprinter) function.

### -field fpEndDocPrinter

(Required.) Pointer to the provider's [EndDocPrinter](/windows/win32/printdocs/enddocprinter) function.

### -field fpAddJob

(Required.) Pointer to the provider's [AddJob](/windows/win32/printdocs/addjob) function.

### -field fpScheduleJob

(Required.) Pointer to the provider's [ScheduleJob](/windows/win32/printdocs/schedulejob) function.

### -field fpGetPrinterData

(Optional. Can be NULL.) Pointer to the provider's [GetPrinterData](/windows/win32/printdocs/getprinterdata) function.

### -field fpSetPrinterData

(Optional. Can be NULL.) Pointer to the provider's [SetPrinterData](/windows/win32/printdocs/setprinterdata) function.

### -field fpWaitForPrinterChange

Obsolete. Must be NULL.

### -field fpClosePrinter

(Required.) Pointer to the provider's [ClosePrinter](/windows/win32/printdocs/closeprinter) function. If a printer change notification object has been created, then the router calls the provider's FindClosePrinterChangeNotification function before calling ClosePrinter.

### -field fpAddForm

(Optional. Can be NULL.) Pointer to the provider's [AddForm](/windows/win32/printdocs/addform) function.

### -field fpDeleteForm

(Optional. Can be NULL.) Pointer to the provider's [DeleteForm](/windows/win32/printdocs/deleteform) function.

### -field fpGetForm

(Optional. Can be NULL.) Pointer to the provider's [GetForm](/windows/win32/printdocs/getform) function.

### -field fpSetForm

(Optional. Can be NULL.) Pointer to the provider's [SetForm](/windows/win32/printdocs/setform) function.

### -field fpEnumForms

(Optional. Can be NULL.) Pointer to the provider's [EnumForms](/windows/win32/printdocs/enumforms) function.

### -field fpEnumMonitors

(Optional. Can be NULL.) Pointer to the provider's [EnumMonitors](/windows/win32/printdocs/enummonitors) function, which is described in the Windows SDK documentation. However, at the provider level this function must supply one of the DWORD return values listed in the following table.

| Return value | Definition |
| --- | --- |
| ROUTER_SUCCESS | The provider has enumerated the monitors on the specified server. |
| ROUTER_STOP_ROUTING | The provider has enumerated the monitors on the specified server, and the router should not call other providers. |
| ROUTER_UNKNOWN | The provider does not support the specified server. |

### -field fpEnumPorts

| Return value | Definition |
| --- | --- |
| ROUTER_SUCCESS | The provider has enumerated the ports on the specified server. |
| ROUTER_STOP_ROUTING | The provider has enumerated the ports on the specified server, and the router should not call other providers. |
| ROUTER_UNKNOWN | The provider does not support the specified server. |

### -field fpAddPort

(Optional. Can be NULL.) Pointer to the provider's [AddPort](/windows/win32/printdocs/addport) function. If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpConfigurePort

(Required.) Pointer to the provider's [ConfigurePort](/windows/win32/printdocs/configureport) function. If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror), the router will attempt to call another provider.

### -field fpDeletePort

(Required.) Pointer to the provider's [DeletePort](/windows/win32/printdocs/deleteport) function. If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpCreatePrinterIC

For internal use only. Must be NULL.

### -field fpPlayGdiScriptOnPrinterIC

For internal use only. Must be NULL.

### -field fpDeletePrinterIC

For internal use only. Must be NULL.

### -field fpAddPrinterConnection

(Optional. Can be NULL.) Pointer to the provider's [AddPrinterConnection](/windows/win32/printdocs/addprinterconnection) function.

### -field fpDeletePrinterConnection

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterConnection](/windows/win32/printdocs/deleteprinterconnection) function.

### -field fpPrinterMessageBox

Not used. Must be NULL.

### -field fpAddMonitor

(Optional. Can be NULL.) Pointer to the provider's [AddMonitor](/windows/win32/printdocs/addmonitor) function. If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpDeleteMonitor

(Optional. Can be NULL.) Pointer to the provider's [DeleteMonitor](/windows/win32/printdocs/addmonitor) function. If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpResetPrinter

(Optional. Can be NULL.) Pointer to the provider's [ResetPrinter](/windows/win32/printdocs/resetprinter) function.

### -field fpGetPrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterDriverEx** function. If **GetPrinterDriverEx** is not supported, the router attempts to call [GetPrinterDriver](/windows/win32/printdocs/getprinterdriver).

### -field fpFindFirstPrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's [FindFirstPrinterChangeNotification](/windows/win32/printdocs/findfirstprinterchangenotification) function.

### -field fpFindClosePrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's [FindClosePrinterChangeNotification](/windows/win32/printdocs/findcloseprinterchangenotification) function.

### -field fpAddPortEx

(Optional. Can be NULL.) Pointer to the provider's **AddPortEx** function. If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpShutDown

For internal use only. Must be NULL.

### -field fpRefreshPrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's [RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85)) function.

### -field fpOpenPrinterEx

For internal use only. Must be NULL.

### -field fpAddPrinterEx

For internal use only. Must be NULL.

### -field fpSetPort

(Optional. Can be NULL.) Pointer to the provider's [SetPort](/windows/win32/printdocs/setport) function. If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror), the router will attempt to call another provider.

### -field fpEnumPrinterData

(Optional. Can be NULL.) Pointer to the provider's [EnumPrinterData](/windows/win32/printdocs/enumprinterdata) function.

### -field fpDeletePrinterData

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterData](/windows/win32/printdocs/deleteprinterdata) function.

### -field fpClusterSplOpen

For internal use only. Must be NULL.

### -field fpClusterSplClose

For internal use only. Must be NULL.

### -field fpClusterSplIsAlive

For internal use only. Must be NULL.

### -field fpSetPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's [SetPrinterDataEx](/windows/win32/printdocs/setprinterdataex) function.

### -field fpGetPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's [GetPrinterDataEx](/windows/win32/printdocs/getprinterdataex) function.

### -field fpEnumPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's [EnumPrinterDataEx](/windows/win32/printdocs/enumprinterdataex) function.

### -field fpEnumPrinterKey

(Optional. Can be NULL.) Pointer to the provider's [EnumPrinterKey](/windows/win32/printdocs/enumprinterkey) function.

### -field fpDeletePrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterDataEx](/windows/win32/printdocs/deleteprinterdataex) function.

### -field fpDeletePrinterKey

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterKey](/windows/win32/printdocs/deleteprinterkey) function.

### -field fpSeekPrinter

For internal use only. Must be NULL.

### -field fpDeletePrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's [DeletePrinterDriverEx](/windows/win32/printdocs/deleteprinterdriverex) function. If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpAddPerMachineConnection

For internal use only. Must be NULL.

### -field fpDeletePerMachineConnection

For internal use only. Must be NULL.

### -field fpEnumPerMachineConnections

For internal use only. Must be NULL.

### -field fpXcvData

(Optional. Can be NULL.) Pointer to the provider's [XcvData](/previous-versions/ff564255(v=vs.85)) function.

### -field fpAddPrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's [AddPrinterDriverEx](/windows/win32/printdocs/addprinterdriverex) function. If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to [SetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-setlasterror) before returning **FALSE**.

### -field fpSplReadPrinter

For internal use only. Must be NULL.

### -field fpDriverUnloadComplete

For internal use only. Must be NULL.

### -field fpGetSpoolFileInfo

For internal use only. Must be NULL.

### -field fpCommitSpoolData

For internal use only. Must be NULL.

### -field fpCloseSpoolFileHandle

For internal use only. Must be NULL.

### -field fpFlushPrinter

For internal use only. Must be NULL.

### -field fpSendRecvBidiData

(Optional. Can be NULL.) Pointer to the provider's [SendRecvBidiData](/previous-versions//ff562068(v=vs.85)) function. If this parameter is NULL, it means that the provider does not support bidi communication.

### -field fpAddPrinterConnection2

For internal use only. Must be NULL.

### -field fpGetPrintClassObject

For internal use only. Must be NULL.

### -field fpReportJobProcessingProgress

For internal use only. Must be NULL.

### -field fpEnumAndLogProvidorObjects

For internal use only. Must be NULL.

### -field fpInternalGetPrinterDriver

For internal use only. Must be NULL.

### -field fpFindCompatibleDriver

For internal use only. Must be NULL.

### -field fpGetJobNamedPropertyValue

For internal use only. Must be NULL.

### -field fpSetJobNamedProperty

For internal use only. Must be NULL.

### -field fpDeleteJobNamedProperty

For internal use only. Must be NULL.

### -field fpEnumJobNamedProperties

For internal use only. Must be NULL.

### -field fpPowerEvent

For internal use only. Must be NULL.

### -field fpGetUserPropertyBag

For internal use only. Must be NULL.

### -field fpCanShutdown

For internal use only. Must be NULL.

### -field fpLogJobInfoForBranchOffice

For internal use only. Must be NULL.

### -field fpRegeneratePrintDeviceCapabilities

For internal use only. Must be NULL.

## -remarks

Function pointers are listed in the order they are specified within the PRINTPROVIDOR structure. To see function descriptions grouped by related capabilities, see [Functions Defined by Print Providers](/windows-hardware/drivers/print/functions-defined-by-print-providers).

## -see-also

[FindFirstPrinterChangeNotification](../winspool/nf-winspool-findfirstprinterchangenotification.md)

[InitializePrintProvidor](./nf-winsplp-initializeprintprovidor.md)

[RefreshPrinterChangeNotification](/previous-versions/ff561930(v=vs.85))

[SendRecvBidiData](/previous-versions//ff562068(v=vs.85))

[XcvData](/previous-versions/ff564255(v=vs.85))


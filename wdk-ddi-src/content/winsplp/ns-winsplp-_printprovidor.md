---
UID: NS:winsplp._PRINTPROVIDOR
title: _PRINTPROVIDOR (winsplp.h)
description: The PRINTPROVIDOR structure is used as a parameter to a print provider's InitializePrintProvidor function.
old-location: print\printprovidor.htm
tech.root: print
ms.assetid: c030cb9d-23c0-4d0e-970f-f447e9af7528
ms.date: 03/19/2019
ms.keywords: "*LPPRINTPROVIDOR, LPPRINTPROVIDOR, LPPRINTPROVIDOR structure pointer [Print Devices], PRINTPROVIDOR, PRINTPROVIDOR structure [Print Devices], _PRINTPROVIDOR, print.printprovidor, spoolfnc_4fb8242e-e0a0-47e5-b01f-2a20932d4d84.xml, winsplp/LPPRINTPROVIDOR, winsplp/PRINTPROVIDOR"
ms.topic: struct
ms.custom: 19H1
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsplp.h
api_name:
- PRINTPROVIDOR
product:
- Windows
targetos: Windows
req.typenames: PRINTPROVIDOR, *LPPRINTPROVIDOR
---

# _PRINTPROVIDOR structure

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

The PRINTPROVIDOR structure is used as a parameter to a print provider's [InitializePrintProvidor](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintprovidor) function. All structure member values are supplied by the provider.

## -struct-fields

### -field fpOpenPrinter

(Required.) Pointer to the provider's **OpenPrinter** function, which is described in the Microsoft Windows SDK documentation. However, at the provider level, this function must supply one of the DWORD return values listed in the following table.

| Return value | Definition |
| --- | --- |
| ROUTER_SUCCESS | The provider supports the specified printer and has opened it. |
| ROUTER_STOP_ROUTING | The provider supports the specified printer, but an error occurred and the printer could not be opened. It is assumed that no other provider can support the printer. The function must call **SetLastError**. |
| ROUTER_UNKNOWN | The provider does not support the specified printer. The function must call **SetLastError** and specify ERROR_INVALID_NAME. |

The router calls each provider until one of them returns ROUTER_SUCCESS or ROUTER_STOP_ROUTING. If the provider returns ROUTER_SUCCESS, it must also return a unique handle. (For more information, see Introduction to Print Providers.) The router first attempts to call the provider's OpenPrinterEx function. If that function is not supported, the router calls OpenPrinter.

### -field fpSetJob

(Required.) Pointer to the provider's **SetJob** function (described in the Windows SDK documentation).

### -field fpGetJob

(Required.) Pointer to the provider's **GetJob** function (described in the Windows SDK documentation).

### -field fpEnumJobs

(Required.) Pointer to the provider's **EnumJobs** function (described in the Windows SDK documentation).

### -field fpAddPrinter

(Optional. Can be NULL.) Pointer to the provider's **AddPrinter** function (described in the Windows SDK documentation).

### -field fpDeletePrinter

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinter** function (described in the Windows SDK documentation).

### -field fpSetPrinter

(Required.) Pointer to the provider's **SetPrinter** function (described in the Windows SDK documentation).

### -field fpGetPrinter

(Required.) Pointer to the provider's **GetPrinter** function (described in the Windows SDK documentation). If you are [writing a network print provider](https://docs.microsoft.com/windows-hardware/drivers/print/writing-a-network-print-provider) and **GetPrinter** is returning a PRINTER_INFO_2 structure, the function should supply only the cJobs and Status structure members. The [local print provider](https://docs.microsoft.com/windows-hardware/drivers/print/local-print-provider)) supplies the rest of the structure members.

### -field fpEnumPrinters

(Required.) Pointer to the provider's **EnumPrinters** function (described in the Windows SDK documentation).

### -field fpAddPrinterDriver

(Optional. Can be NULL.) Pointer to the provider's **AddPrinterDriver** function (described in the Windows SDK documentation). If the provider does not support the specified driver or server, it should specify ERROR_INVALID_NAME to SetLastError before returning **FALSE**.

### -field fpEnumPrinterDrivers

(Optional. Can be NULL.) Pointer to the provider's **EnumPrinterDrivers** function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to SetLastError before returning **FALSE**.

### -field fpGetPrinterDriver

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterDriver** function (described in the Windows SDK documentation). The router first attempts to call the provider's **GetPrinterDriverEx** function. If that function is not supported, the router calls **GetPrinterDriver**.

### -field fpGetPrinterDriverDirectory

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterDriverDirectory** function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to **SetLastError** before returning **FALSE**.

### -field fpDeletePrinterDriver

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinterDriver** function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to **SetLastError** before returning **FALSE**.

### -field fpAddPrintProcessor

(Optional. Can be NULL.) Pointer to the provider's **AddPrintProcessor** function (described in the Windows SDK documentation).

### -field fpEnumPrintProcessors

(Optional. Can be NULL.) Pointer to the provider's **EnumPrintProcessors** function (described in the Windows SDK documentation).

### -field fpGetPrintProcessorDirectory

(Optional. Can be NULL.) Pointer to the provider's **GetPrintProcessorDirectory** function (described in the Windows SDK documentation).

### -field fpDeletePrintProcessor

(Optional. Can be NULL.) Pointer to the provider's **DeletePrintProcessor** function (described in the Windows SDK documentation).

### -field fpEnumPrintProcessorDatatypes

(Optional. Can be NULL.) Pointer to the provider's **EnumPrintProcessorDatatypes** function (described in the Windows SDK documentation).

### -field fpStartDocPrinter

(Required.) Pointer to the provider's **StartDocPrinter** function (described in the Windows SDK documentation).

### -field fpStartPagePrinter

(Optional. Can be NULL.) Pointer to the provider's **StartPagePrinter** function (described in the Windows SDK documentation).

### -field fpWritePrinter

(Required.) Pointer to the provider's **WritePrinter** function (described in the Windows SDK documentation).

### -field fpEndPagePrinter

(Optional. Can be NULL.) Pointer to the provider's **EndPagePrinter** function (described in the Windows SDK documentation).

### -field fpAbortPrinter

(Required.) Pointer to the provider's **AbortPrinter** function (described in the Windows SDK documentation).

### -field fpReadPrinter

(Optional. Can be NULL.) Pointer to the provider's **ReadPrinter** function (described in the Windows SDK documentation).

### -field fpEndDocPrinter

(Required.) Pointer to the provider's **EndDocPrinter** function (described in the Windows SDK documentation).

### -field fpAddJob

(Required.) Pointer to the provider's **AddJob** function (described in the Windows SDK documentation).

### -field fpScheduleJob

(Required.) Pointer to the provider's **ScheduleJob** function (described in the Windows SDK documentation).

### -field fpGetPrinterData

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterData** function (described in the Windows SDK documentation).

### -field fpSetPrinterData

(Optional. Can be NULL.) Pointer to the provider's **SetPrinterData** function (described in the Windows SDK documentation).

### -field fpWaitForPrinterChange

Obsolete. Must be NULL.

### -field fpClosePrinter

(Required.) Pointer to the provider's **ClosePrinter** function (described in the Windows SDK documentation). If a printer change notification object has been created, then the router calls the provider's FindClosePrinterChangeNotification function (described in the Windows SDK documentation) before calling ClosePrinter.

### -field fpAddForm

(Optional. Can be NULL.) Pointer to the provider's **AddForm** function (described in the Windows SDK documentation).

### -field fpDeleteForm

(Optional. Can be NULL.) Pointer to the provider's **DeleteForm** function (described in the Windows SDK documentation).

### -field fpGetForm

(Optional. Can be NULL.) Pointer to the provider's **GetForm** function (described in the Windows SDK documentation).

### -field fpSetForm

(Optional. Can be NULL.) Pointer to the provider's **SetForm** function (described in the Windows SDK documentation).

### -field fpEnumForms

(Optional. Can be NULL.) Pointer to the provider's **EnumForms** function (described in the Windows SDK documentation).

### -field fpEnumMonitors

(Optional. Can be NULL.) Pointer to the provider's **EnumMonitors** function, which is described in the Windows SDK documentation. However, at the provider level this function must supply one of the DWORD return values listed in the following table.

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

(Optional. Can be NULL.) Pointer to the provider's **AddPort** function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning **FALSE**.

### -field fpConfigurePort

(Required.) Pointer to the provider's **ConfigurePort** function (described in the Windows SDK documentation). If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to SetLastError, the router will attempt to call another provider.

### -field fpDeletePort

(Required.) Pointer to the provider's **DeletePort** function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning **FALSE**.

### -field fpCreatePrinterIC

For internal use only. Must be NULL.

### -field fpPlayGdiScriptOnPrinterIC

For internal use only. Must be NULL.

### -field fpDeletePrinterIC

For internal use only. Must be NULL.

### -field fpAddPrinterConnection

(Optional. Can be NULL.) Pointer to the provider's **AddPrinterConnection** function (described in the Windows SDK documentation).

### -field fpDeletePrinterConnection

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinterConnection** function (described in the Windows SDK documentation).

### -field fpPrinterMessageBox

Not used. Must be NULL.

### -field fpAddMonitor

(Optional. Can be NULL.) Pointer to the provider's **AddMonitor** function (described in the Windows SDK documentation). If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to SetLastError before returning **FALSE**.

### -field fpDeleteMonitor

(Optional. Can be NULL.) Pointer to the provider's **DeleteMonitor** function (described in the Windows SDK documentation). If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to SetLastError before returning **FALSE**.

### -field fpResetPrinter

(Optional. Can be NULL.) Pointer to the provider's **ResetPrinter** function (described in the Windows SDK documentation).

### -field fpGetPrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterDriverEx** function (described in the Windows SDK documentation). If GetPrinterDriverEx is not supported, the router attempts to call GetPrinterDriver.

### -field fpFindFirstPrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's **FindFirstPrinterChangeNotification** function (described in the Windows SDK documentation).

### -field fpFindClosePrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's **FindClosePrinterChangeNotification** function (described in the Windows SDK documentation).

### -field fpAddPortEx

(Optional. Can be NULL.) Pointer to the provider's **AddPortEx** function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning **FALSE**.

### -field fpShutDown

For internal use only. Must be NULL.

### -field fpRefreshPrinterChangeNotification

(Optional. Can be NULL.) Pointer to the provider's **RefreshPrinterChangeNotification** function.

### -field fpOpenPrinterEx

For internal use only. Must be NULL.

### -field fpAddPrinterEx

For internal use only. Must be NULL.

### -field fpSetPort

(Optional. Can be NULL.) Pointer to the provider's **SetPort** function (described in the Windows SDK documentation). If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to **SetLastError**, the router will attempt to call another provider.

### -field fpEnumPrinterData

(Optional. Can be NULL.) Pointer to the provider's **EnumPrinterData** function (described in the Windows SDK documentation).

### -field fpDeletePrinterData

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinterData** function (described in the Windows SDK documentation).

### -field fpClusterSplOpen

For internal use only. Must be NULL.

### -field fpClusterSplClose

For internal use only. Must be NULL.

### -field fpClusterSplIsAlive

For internal use only. Must be NULL.

### -field fpSetPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's **SetPrinterDataEx** function (described in the Windows SDK documentation).

### -field fpGetPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's **GetPrinterDataEx** function (described in the Windows SDK documentation).

### -field fpEnumPrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's **EnumPrinterDataEx** function (described in the Windows SDK documentation).

### -field fpEnumPrinterKey

(Optional. Can be NULL.) Pointer to the provider's **EnumPrinterKey** function (described in the Windows SDK documentation).

### -field fpDeletePrinterDataEx

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinterDataEx** function (described in the Windows SDK documentation).

### -field fpDeletePrinterKey

(Optional. Can be NULL.) Pointer to the provider's **DeletePrinterKey** function (described in the Windows SDK documentation).

### -field fpSeekPrinter

For internal use only. Must be NULL.

### -field fpDeletePrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's DeletePrinterDriverEx function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to **SetLastError** before returning **FALSE**.

### -field fpAddPerMachineConnection

For internal use only. Must be NULL.

### -field fpDeletePerMachineConnection

For internal use only. Must be NULL.

### -field fpEnumPerMachineConnections

For internal use only. Must be NULL.

### -field fpXcvData

(Optional. Can be NULL.) Pointer to the provider's **XcvData** function.

### -field fpAddPrinterDriverEx

(Optional. Can be NULL.) Pointer to the provider's **AddPrinterDriverEx** function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to SetLastError before returning **FALSE**.

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

(Optional. Can be NULL.) Pointer to the provider's **SendRecvBidiData** function. If this parameter is NULL, it means that the provider does not support bidi communication.

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

Function pointers are listed in the order they are specified within the PRINTPROVIDOR structure. To see function descriptions grouped by related capabilities, see [Functions Defined by Print Providers](https://docs.microsoft.com/windows-hardware/drivers/print/functions-defined-by-print-providers).

## -see-also

[FindFirstPrinterChangeNotification](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winspool/nf-winspool-findfirstprinterchangenotification)

[InitializePrintProvidor](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/winsplp/nf-winsplp-initializeprintprovidor)

[RefreshPrinterChangeNotification](https://msdn.microsoft.com/library/windows/hardware/ff561930)

[SendRecvBidiData](href="https://msdn.microsoft.com/library/windows/hardware/ff562068)

[XcvData](href="https://msdn.microsoft.com/library/windows/hardware/ff564255)

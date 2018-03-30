---
UID: NS:winsplp._PRINTPROVIDOR
title: "_PRINTPROVIDOR"
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\printprovidor.htm
old-project: print
ms.assetid: c030cb9d-23c0-4d0e-970f-f447e9af7528
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPPRINTPROVIDOR, LPPRINTPROVIDOR, LPPRINTPROVIDOR structure pointer [Print Devices], PRINTPROVIDOR, PRINTPROVIDOR structure [Print Devices], _PRINTPROVIDOR, print.printprovidor, spoolfnc_4fb8242e-e0a0-47e5-b01f-2a20932d4d84.xml, winsplp/LPPRINTPROVIDOR, winsplp/PRINTPROVIDOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	PRINTPROVIDOR
product: Windows
targetos: Windows
req.typenames: PRINTPROVIDOR, *LPPRINTPROVIDOR
req.product: Windows 10 or later.
---

# _PRINTPROVIDOR structure


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>The PRINTPROVIDOR structure is used as a parameter to a print provider's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551614">InitializePrintProvidor</a> function. All structure member values are supplied by the provider.


## -struct-fields




### -field fpOpenPrinter

(Required.) Pointer to the provider's <b>OpenPrinter</b> function, which is described in the Microsoft Windows SDK documentation. However, at the provider level, this function must supply one of the DWORD return values listed in the following table.

<table>
<tr>
<th>Return value</th>
<th>Definition</th>
</tr>
<tr>
<td>ROUTER_SUCCESS</td>
<td>The provider supports the specified printer and has opened it.</td>
</tr>
<tr>
<td>ROUTER_STOP_ROUTING</td>
<td>The provider supports the specified printer, but an error occurred and the printer could not be opened. It is assumed that no other provider can support the printer. The function must call <b>SetLastError</b>.</td>
</tr>
<tr>
<td>ROUTER_UNKNOWN </td>
<td>The provider does not support the specified printer. The function must call <b>SetLastError</b> and specify ERROR_INVALID_NAME.</td>
</tr>
</table>
 

The router calls each provider until one of them returns ROUTER_SUCCESS or ROUTER_STOP_ROUTING. If the provider returns ROUTER_SUCCESS, it must also return a unique handle. (For more information, see Introduction to Print Providers.) The router first attempts to call the provider's OpenPrinterEx function. If that function is not supported, the router calls OpenPrinter.


### -field fpSetJob

(Required.) Pointer to the provider's <b>SetJob</b> function (described in the Windows SDK documentation).


### -field fpGetJob

(Required.) Pointer to the provider's <b>GetJob</b> function (described in the Windows SDK documentation).


### -field fpEnumJobs

(Required.) Pointer to the provider's <b>EnumJobs</b> function (described in the Windows SDK documentation).


### -field fpAddPrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPrinter</b> function (described in the Windows SDK documentation).


### -field fpDeletePrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinter</b> function (described in the Windows SDK documentation).


### -field fpSetPrinter

(Required.) Pointer to the provider's <b>SetPrinter</b> function (described in the Windows SDK documentation).


### -field fpGetPrinter

(Required.) Pointer to the provider's <b>GetPrinter</b> function (described in the Windows SDK documentation). If you are <a href="https://msdn.microsoft.com/9dbe8a00-6b5f-41ae-8ab5-218dcbe37833">writing a network print provider</a> and <b>GetPrinter</b> is returning a PRINTER_INFO_2 structure, the function should supply only the cJobs and Status structure members. The <a href="https://msdn.microsoft.com/c6f9ba42-5f0f-4919-bfac-e4cd1045de4d">local print provider</a> supplies the rest of the structure members.


### -field fpEnumPrinters

(Required.) Pointer to the provider's <b>EnumPrinters</b> function (described in the Windows SDK documentation).


### -field fpAddPrinterDriver

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPrinterDriver</b> function (described in the Windows SDK documentation). If the provider does not support the specified driver or server, it should specify ERROR_INVALID_NAME to SetLastError before returning <b>FALSE</b>.


### -field fpEnumPrinterDrivers

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrinterDrivers</b> function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to SetLastError before returning <b>FALSE</b>.


### -field fpGetPrinterDriver

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrinterDriver</b> function (described in the Windows SDK documentation). The router first attempts to call the provider's <b>GetPrinterDriverEx</b> function. If that function is not supported, the router calls <b>GetPrinterDriver</b>.


### -field fpGetPrinterDriverDirectory

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrinterDriverDirectory</b> function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to <b>SetLastError</b> before returning <b>FALSE</b>.


### -field fpDeletePrinterDriver

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinterDriver</b> function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to <b>SetLastError</b> before returning <b>FALSE</b>.


### -field fpAddPrintProcessor

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPrintProcessor</b> function (described in the Windows SDK documentation).


### -field fpEnumPrintProcessors

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrintProcessors</b> function (described in the Windows SDK documentation).


### -field fpGetPrintProcessorDirectory

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrintProcessorDirectory</b> function (described in the Windows SDK documentation).


### -field fpDeletePrintProcessor

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrintProcessor</b> function (described in the Windows SDK documentation).


### -field fpEnumPrintProcessorDatatypes

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrintProcessorDatatypes</b> function (described in the Windows SDK documentation).


### -field fpStartDocPrinter

(Required.) Pointer to the provider's <b>StartDocPrinter</b> function (described in the Windows SDK documentation).


### -field fpStartPagePrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>StartPagePrinter</b> function (described in the Windows SDK documentation).


### -field fpWritePrinter

(Required.) Pointer to the provider's <b>WritePrinter</b> function (described in the Windows SDK documentation).


### -field fpEndPagePrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EndPagePrinter</b> function (described in the Windows SDK documentation).


### -field fpAbortPrinter

(Required.) Pointer to the provider's <b>AbortPrinter</b> function (described in the Windows SDK documentation).


### -field fpReadPrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>ReadPrinter</b> function (described in the Windows SDK documentation).


### -field fpEndDocPrinter

(Required.) Pointer to the provider's <b>EndDocPrinter</b> function (described in the Windows SDK documentation).


### -field fpAddJob

(Required.) Pointer to the provider's <b>AddJob</b> function (described in the Windows SDK documentation).


### -field fpScheduleJob

(Required.) Pointer to the provider's <b>ScheduleJob</b> function (described in the Windows SDK documentation).


### -field fpGetPrinterData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrinterData</b> function (described in the Windows SDK documentation).


### -field fpSetPrinterData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>SetPrinterData</b> function (described in the Windows SDK documentation).


### -field fpWaitForPrinterChange

Obsolete. Must be <b>NULL</b>.


### -field fpClosePrinter

(Required.) Pointer to the provider's <b>ClosePrinter</b> function (described in the Windows SDK documentation). If a printer change notification object has been created, then the router calls the provider's FindClosePrinterChangeNotification function (described in the Windows SDK documentation) before calling ClosePrinter.


### -field fpAddForm

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddForm</b> function (described in the Windows SDK documentation).


### -field fpDeleteForm

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeleteForm</b> function (described in the Windows SDK documentation).


### -field fpGetForm

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetForm</b> function (described in the Windows SDK documentation).


### -field fpSetForm

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>SetForm</b> function (described in the Windows SDK documentation).


### -field fpEnumForms

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumForms</b> function (described in the Windows SDK documentation).


### -field fpEnumMonitors

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumMonitors</b> function, which is described in the Windows SDK documentation. However, at the provider level this function must supply one of the DWORD return values listed in the following table.

<table>
<tr>
<th>Return value</th>
<th>Definition</th>
</tr>
<tr>
<td>ROUTER_SUCCESS</td>
<td>The provider has enumerated the monitors on the specified server.</td>
</tr>
<tr>
<td>ROUTER_STOP_ROUTING</td>
<td>The provider has enumerated the monitors on the specified server, and the router should not call other providers.</td>
</tr>
<tr>
<td>ROUTER_UNKNOWN </td>
<td>The provider does not support the specified server.</td>
</tr>
</table>
 


### -field fpEnumPorts

<table>
<tr>
<th>Return value</th>
<th>Definition</th>
</tr>
<tr>
<td>ROUTER_SUCCESS</td>
<td>The provider has enumerated the ports on the specified server.</td>
</tr>
<tr>
<td>ROUTER_STOP_ROUTING</td>
<td>The provider has enumerated the ports on the specified server, and the router should not call other providers.</td>
</tr>
<tr>
<td>ROUTER_UNKNOWN </td>
<td>The provider does not support the specified server.</td>
</tr>
</table>
 


### -field fpAddPort

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPort</b> function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning <b>FALSE</b>.


### -field fpConfigurePort

(Required.) Pointer to the provider's <b>ConfigurePort</b> function (described in the Windows SDK documentation). If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to SetLastError, the router will attempt to call another provider.


### -field fpDeletePort

(Required.) Pointer to the provider's <b>DeletePort</b> function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning <b>FALSE</b>.


### -field fpCreatePrinterIC

For internal use only. Must be <b>NULL</b>.


### -field fpPlayGdiScriptOnPrinterIC

For internal use only. Must be <b>NULL</b>.


### -field fpDeletePrinterIC

For internal use only. Must be <b>NULL</b>.


### -field fpAddPrinterConnection

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPrinterConnection</b> function (described in the Windows SDK documentation).


### -field fpDeletePrinterConnection

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinterConnection</b> function (described in the Windows SDK documentation).


### -field fpPrinterMessageBox

Not used. Must be <b>NULL</b>.


### -field fpAddMonitor

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddMonitor</b> function (described in the Windows SDK documentation). If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to SetLastError before returning <b>FALSE</b>.


### -field fpDeleteMonitor

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeleteMonitor</b> function (described in the Windows SDK documentation). If the provider does not support the specified monitor, it must supply ERROR_INVALID_NAME to SetLastError before returning <b>FALSE</b>.


### -field fpResetPrinter

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>ResetPrinter</b> function (described in the Windows SDK documentation).


### -field fpGetPrinterDriverEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrinterDriverEx</b> function (described in the Windows SDK documentation). If GetPrinterDriverEx is not supported, the router attempts to call GetPrinterDriver.


### -field fpFindFirstPrinterChangeNotification

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>FindFirstPrinterChangeNotification</b> function (described in the Windows SDK documentation).


### -field fpFindClosePrinterChangeNotification

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>FindClosePrinterChangeNotification</b> function (described in the Windows SDK documentation).


### -field fpAddPortEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPortEx</b> function (described in the Windows SDK documentation). If the provider does not support the specified port, it must supply ERROR_NOT_SUPPORTED to SetLastError before returning <b>FALSE</b>.


### -field fpShutDown

For internal use only. Must be <b>NULL</b>.


### -field fpRefreshPrinterChangeNotification

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>RefreshPrinterChangeNotification</b> function.


### -field fpOpenPrinterEx

For internal use only. Must be <b>NULL</b>.


### -field fpAddPrinterEx

For internal use only. Must be <b>NULL</b>.


### -field fpSetPort

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>SetPort</b> function (described in the Windows SDK documentation). If the function supplies ERROR_NOT_SUPPORTED, ERROR_INVALID_NAME, or ERROR_UNKNOWN_PORT to <b>SetLastError</b>, the router will attempt to call another provider.


### -field fpEnumPrinterData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrinterData</b> function (described in the Windows SDK documentation).


### -field fpDeletePrinterData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinterData</b> function (described in the Windows SDK documentation).


### -field fpClusterSplOpen

For internal use only. Must be <b>NULL</b>.


### -field fpClusterSplClose

For internal use only. Must be <b>NULL</b>.


### -field fpClusterSplIsAlive

For internal use only. Must be <b>NULL</b>.


### -field fpSetPrinterDataEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>SetPrinterDataEx</b> function (described in the Windows SDK documentation).


### -field fpGetPrinterDataEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>GetPrinterDataEx</b> function (described in the Windows SDK documentation).


### -field fpEnumPrinterDataEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrinterDataEx</b> function (described in the Windows SDK documentation).


### -field fpEnumPrinterKey

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>EnumPrinterKey</b> function (described in the Windows SDK documentation).


### -field fpDeletePrinterDataEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinterDataEx</b> function (described in the Windows SDK documentation).


### -field fpDeletePrinterKey

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>DeletePrinterKey</b> function (described in the Windows SDK documentation).


### -field fpSeekPrinter

For internal use only. Must be <b>NULL</b>.


### -field fpDeletePrinterDriverEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's DeletePrinterDriverEx function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to <b>SetLastError</b> before returning <b>FALSE</b>.


### -field fpAddPerMachineConnection

For internal use only. Must be <b>NULL</b>.


### -field fpDeletePerMachineConnection

For internal use only. Must be <b>NULL</b>.


### -field fpEnumPerMachineConnections

For internal use only. Must be <b>NULL</b>.


### -field fpXcvData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>XcvData</b> function.


### -field fpAddPrinterDriverEx

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>AddPrinterDriverEx</b> function (described in the Windows SDK documentation). If the provider does not support the specified server, it should specify ERROR_INVALID_NAME to SetLastError before returning <b>FALSE</b>.


### -field fpSplReadPrinter

For internal use only. Must be <b>NULL</b>.


### -field fpDriverUnloadComplete

For internal use only. Must be <b>NULL</b>.


### -field fpGetSpoolFileInfo

For internal use only. Must be <b>NULL</b>.


### -field fpCommitSpoolData

For internal use only. Must be <b>NULL</b>.


### -field fpCloseSpoolFileHandle

For internal use only. Must be <b>NULL</b>.


### -field fpFlushPrinter

For internal use only. Must be <b>NULL</b>.


### -field fpSendRecvBidiData

(Optional. Can be <b>NULL</b>.) Pointer to the provider's <b>SendRecvBidiData</b> function. If this parameter is <b>NULL</b>, it means that the provider does not support bidi communication.


### -field fpAddPrinterConnection2

 


### -field fpGetPrintClassObject

 


### -field fpReportJobProcessingProgress

 


### -field fpEnumAndLogProvidorObjects

 


### -field fpInternalGetPrinterDriver

 


### -field fpFindCompatibleDriver

 


### -field fpGetJobNamedPropertyValue

 


### -field fpSetJobNamedProperty

 


### -field fpDeleteJobNamedProperty

 


### -field fpEnumJobNamedProperties

 


### -field fpPowerEvent

 


### -field fpGetUserPropertyBag

 


### -field fpCanShutdown

 


### -field fpLogJobInfoForBranchOffice

 




## -remarks



Function pointers are listed in the order they are specified within the PRINTPROVIDOR structure. To see function descriptions grouped by related capabilities, see <a href="https://msdn.microsoft.com/4fae4b69-ed4b-47b6-b6e8-41733aed51a5">Functions Defined by Print Providers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548837">FindFirstPrinterChangeNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551614">InitializePrintProvidor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561930">RefreshPrinterChangeNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562068">SendRecvBidiData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564255">XcvData</a>
 

 


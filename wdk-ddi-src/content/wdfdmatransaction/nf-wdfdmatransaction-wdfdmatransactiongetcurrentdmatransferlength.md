---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetCurrentDmaTransferLength
title: WdfDmaTransactionGetCurrentDmaTransferLength function (wdfdmatransaction.h)
description: The WdfDmaTransactionGetCurrentDmaTransferLength method returns the size of the current DMA transfer.
old-location: wdf\wdfdmatransactiongetcurrentdmatransferlength.htm
tech.root: wdf
ms.assetid: 20a27ad7-0b27-494e-b761-fc3edf71e8c9
ms.date: 02/26/2018
ms.keywords: DFDmaObjectRef_e0fc16e5-9adb-44c5-be53-5e7929ede3aa.xml, WdfDmaTransactionGetCurrentDmaTransferLength, WdfDmaTransactionGetCurrentDmaTransferLength method, kmdf.wdfdmatransactiongetcurrentdmatransferlength, wdf.wdfdmatransactiongetcurrentdmatransferlength, wdfdmatransaction/WdfDmaTransactionGetCurrentDmaTransferLength
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDmaTransactionGetCurrentDmaTransferLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionGetCurrentDmaTransferLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetCurrentDmaTransferLength</b> method returns the size of the current DMA transfer.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


## -returns



<b>WdfDmaTransactionGetCurrentDmaTransferLength</b> returns the length of the current DMA transfer.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If a driver calls <b>WdfDmaTransactionGetCurrentDmaTransferLength</b>, it must do so before it calls one of the transfer completion routines, such as <a href="https://msdn.microsoft.com/library/windows/hardware/ff547039">WdfDmaTransactionDmaCompleted</a>, to complete the current DMA transfer. Typically, drivers call <b>WdfDmaTransactionGetCurrentDmaTransferLength</b> from within an <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> event callback function.

Typically, a driver calls <b>WdfDmaTransactionGetCurrentDmaTransferLength</b> for devices that report residual DMA transfer lengths (that is, byte counts of data that was not transferred). By subtracting the residual transfer length from the value that <b>WdfDmaTransactionGetCurrentDmaTransferLength</b> returned, the driver can determine the actual transfer length. The driver then calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff547052">WdfDmaTransactionDmaCompletedWithLength</a> to let the framework know the number of bytes that the device actually transferred.

For more information about complete DMA transfers, see <a href="https://msdn.microsoft.com/86383b9f-9b82-4afa-81ac-2ab09bd8778b">Completing a DMA Transfer</a>. 


#### Examples

For a code example that uses <b>WdfDmaTransactionGetCurrentDmaTransferLength</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547052">WdfDmaTransactionDmaCompletedWithLength</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547039">WdfDmaTransactionDmaCompleted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547052">WdfDmaTransactionDmaCompletedWithLength</a>
 

 


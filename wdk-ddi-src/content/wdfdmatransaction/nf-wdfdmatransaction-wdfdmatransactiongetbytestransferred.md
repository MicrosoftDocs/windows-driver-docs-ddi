---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetBytesTransferred
title: WdfDmaTransactionGetBytesTransferred function
author: windows-driver-content
description: The WdfDmaTransactionGetBytesTransferred method returns the total number of bytes that have been transferred for a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetbytestransferred.htm
old-project: wdf
ms.assetid: 32cc50bc-a93b-43ec-98c7-bfaaebbe6c28
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_a8d61436-75d3-4c14-a81b-6ba7adb3c442.xml, WdfDmaTransactionGetBytesTransferred, WdfDmaTransactionGetBytesTransferred method, kmdf.wdfdmatransactiongetbytestransferred, wdf.wdfdmatransactiongetbytestransferred, wdfdmatransaction/WdfDmaTransactionGetBytesTransferred
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfDmaTransactionGetBytesTransferred
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionGetBytesTransferred function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionGetBytesTransferred</b> method returns the total number of bytes that have been transferred for a specified DMA transaction.  


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


## -returns



<b>WdfDmaTransactionGetBytesTransferred</b> returns the total number of bytes that have been transferred for the DMA transaction that the <i>DmaTransaction</i> parameter specified.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Framework-based drivers typically call <b>WdfDmaTransactionGetBytesTransferred</b> from within an <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> event callback function, after all DMA transfers are complete, to obtain the final transferred byte count. Drivers typically use the final byte count as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a> method. For more information about this method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/completing-a-dma-transaction">Completing a DMA Transaction</a>.


#### Examples

For a code example that uses <b>WdfDmaTransactionGetBytesTransferred</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547039">WdfDmaTransactionDmaCompleted</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547039">WdfDmaTransactionDmaCompleted</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549948">WdfRequestCompleteWithInformation</a>
 

 


---
UID: NF:wdfdmatransaction.WdfDmaTransactionRelease
title: WdfDmaTransactionRelease function
author: windows-driver-content
description: The WdfDmaTransactionRelease method terminates a specified DMA transaction without deleting the associated DMA transaction object.
old-location: wdf\wdfdmatransactionrelease.htm
tech.root: wdf
ms.assetid: b271e095-1ac5-4795-82b0-954a17df334a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDmaObjectRef_24ae3a95-d8b5-4a41-874a-ef537ed4c4cd.xml, WdfDmaTransactionRelease, WdfDmaTransactionRelease method, kmdf.wdfdmatransactionrelease, wdf.wdfdmatransactionrelease, wdfdmatransaction/WdfDmaTransactionRelease
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
-	WdfDmaTransactionRelease
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionRelease function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionRelease</b> method terminates a specified DMA transaction without deleting the associated DMA transaction object.  


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>.


## -returns



<b>WdfDmaTransactionRelease</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver has already released or deleted the transaction object that the <i>DmaTransaction</i> parameter specified.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfDmaTransactionRelease</b> method flushes transfer buffers and releases all of the system resources that are associated with the DMA transaction. The transaction object is not deleted and can be reused. For more information about reusing transaction objects, see <a href="https://msdn.microsoft.com/4adb8653-48b6-4e22-aba3-b909c95b8d15">Reusing DMA Transaction Objects</a>.


          If <b>WdfDmaTransactionInitialize<i>Xxx</i></b> returns success but <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a> returns an error value, your driver must call <b>WdfDmaTransactionRelease</b>.


#### Examples

The following code example terminates the DMA transaction that the specified DMA transaction object represents, but it does not delete the DMA transaction object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS  status;

status = WdfDmaTransactionRelease(dmaTransaction);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547027">WdfDmaTransactionCreate</a>
 

 


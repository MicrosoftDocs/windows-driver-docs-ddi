---
UID: NF:wdfdmatransaction.WdfDmaTransactionRelease
title: WdfDmaTransactionRelease function
author: windows-driver-content
description: The WdfDmaTransactionRelease method terminates a specified DMA transaction without deleting the associated DMA transaction object.
old-location: wdf\wdfdmatransactionrelease.htm
old-project: wdf
ms.assetid: b271e095-1ac5-4795-82b0-954a17df334a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdmatransaction/WdfDmaTransactionRelease, DFDmaObjectRef_24ae3a95-d8b5-4a41-874a-ef537ed4c4cd.xml, PFN_WDFDMATRANSACTIONRELEASE, wdf.wdfdmatransactionrelease, WdfDmaTransactionRelease, WdfDmaTransactionRelease method, kmdf.wdfdmatransactionrelease
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionRelease
product: Windows
targetos: Windows
req.typenames: "*PWDF_DMA_SYSTEM_PROFILE_CONFIG, WDF_DMA_SYSTEM_PROFILE_CONFIG"
req.product: Windows 10 or later.
---

# WdfDmaTransactionRelease function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionRelease</b> method terminates a specified DMA transaction without deleting the associated DMA transaction object.  


## -syntax


````
NTSTATUS WdfDmaTransactionRelease(
  _In_ WDFDMATRANSACTION DmaTransaction
);
````


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>.


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


          If <b>WdfDmaTransactionInitialize<i>Xxx</i></b> returns success but <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a> returns an error value, your driver must call <b>WdfDmaTransactionRelease</b>.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactioncreate.md">WdfDmaTransactionCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionRelease method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


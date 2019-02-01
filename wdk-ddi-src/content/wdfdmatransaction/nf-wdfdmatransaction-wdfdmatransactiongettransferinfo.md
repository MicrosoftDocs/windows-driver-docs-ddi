---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetTransferInfo
title: WdfDmaTransactionGetTransferInfo function (wdfdmatransaction.h)
description: The WdfDmaTransactionGetTransferInfo method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.
old-location: wdf\wdfdmatransactiongettransferinfo.htm
tech.root: wdf
ms.assetid: 9EE04529-D322-4498-B802-BB6A53FBC716
ms.date: 02/26/2018
ms.keywords: WdfDmaTransactionGetTransferInfo, WdfDmaTransactionGetTransferInfo method, kmdf.wdfdmatransactiongettransferinfo, wdf.wdfdmatransactiongettransferinfo, wdfdmatransaction/WdfDmaTransactionGetTransferInfo
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
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
-	WdfDmaTransactionGetTransferInfo
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionGetTransferInfo function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetTransferInfo</b> method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to an initialized DMA transaction object.


### -param MapRegisterCount [out, optional]

A caller-supplied location that, on return, contains the number of map registers required for the specified transaction. This parameter is optional and can be NULL.


### -param ScatterGatherElementCount [out, optional]

A caller-supplied location that, on return, contains the number of scatter/gather elements required for the specified transaction. This parameter is optional and can be NULL.


## -returns



This method does not return a value.




## -remarks



The driver might call <b>WdfDmaTransactionGetTransferInfo</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>.

When using DMA version 3, this method returns an accurate count of the number of map registers needed. When using earlier DMA versions, this method assumes that each page requires a map register.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451123">WdfDmaTransactionAllocateResources</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547062">WdfDmaTransactionExecute</a>
 

 


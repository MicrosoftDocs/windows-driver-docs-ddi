---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetTransferInfo
title: WdfDmaTransactionGetTransferInfo function
author: windows-driver-content
description: The WdfDmaTransactionGetTransferInfo method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.
old-location: wdf\wdfdmatransactiongettransferinfo.htm
old-project: wdf
ms.assetid: 9EE04529-D322-4498-B802-BB6A53FBC716
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDmaTransactionGetTransferInfo method, kmdf.wdfdmatransactiongettransferinfo, WdfDmaTransactionGetTransferInfo, PFN_WDFDMATRANSACTIONGETTRANSFERINFO, wdf.wdfdmatransactiongettransferinfo, wdfdmatransaction/WdfDmaTransactionGetTransferInfo
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDmaTransactionGetTransferInfo
product: Windows
targetos: Windows
req.typenames: WDF_DMA_SYSTEM_PROFILE_CONFIG, *PWDF_DMA_SYSTEM_PROFILE_CONFIG
req.product: Windows 10 or later.
---

# WdfDmaTransactionGetTransferInfo function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDmaTransactionGetTransferInfo</b> method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.


## -syntax


````
void WdfDmaTransactionGetTransferInfo(
  _In_      WDFDMATRANSACTION DmaTransaction,
  _Out_opt_ ULONG             *MapRegisterCount,
  _Out_opt_ ULONG             *ScatterGatherElementCount
);
````


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


The driver might call <b>WdfDmaTransactionGetTransferInfo</b> before calling <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a> or <a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>.

When using DMA version 3, this method returns an accurate count of the number of map registers needed. When using earlier DMA versions, this method assumes that each page requires a map register.



## -see-also

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionallocateresources.md">WdfDmaTransactionAllocateResources</a>

<a href="..\wdfdmatransaction\nf-wdfdmatransaction-wdfdmatransactionexecute.md">WdfDmaTransactionExecute</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionGetTransferInfo method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


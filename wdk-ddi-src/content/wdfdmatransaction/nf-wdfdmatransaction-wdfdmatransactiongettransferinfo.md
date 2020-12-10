---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetTransferInfo
title: WdfDmaTransactionGetTransferInfo function (wdfdmatransaction.h)
description: The WdfDmaTransactionGetTransferInfo method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.
old-location: wdf\wdfdmatransactiongettransferinfo.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionGetTransferInfo function"]
ms.keywords: WdfDmaTransactionGetTransferInfo, WdfDmaTransactionGetTransferInfo method, kmdf.wdfdmatransactiongettransferinfo, wdf.wdfdmatransactiongettransferinfo, wdfdmatransaction/WdfDmaTransactionGetTransferInfo
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDmaTransactionGetTransferInfo
 - wdfdmatransaction/WdfDmaTransactionGetTransferInfo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDmaTransactionGetTransferInfo
---

# WdfDmaTransactionGetTransferInfo function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetTransferInfo</b> method returns the number of map registers and scatter/gather list entries required for an initialized DMA transaction.

## -parameters

### -param DmaTransaction 

[in]
A handle to an initialized DMA transaction object.

### -param MapRegisterCount 

[out, optional]
A caller-supplied location that, on return, contains the number of map registers required for the specified transaction. This parameter is optional and can be NULL.

### -param ScatterGatherElementCount 

[out, optional]
A caller-supplied location that, on return, contains the number of scatter/gather elements required for the specified transaction. This parameter is optional and can be NULL.

## -remarks

The driver might call <b>WdfDmaTransactionGetTransferInfo</b> before calling <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a> or <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>.

When using DMA version 3, this method returns an accurate count of the number of map registers needed. When using earlier DMA versions, this method assumes that each page requires a map register.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>



<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionexecute">WdfDmaTransactionExecute</a>

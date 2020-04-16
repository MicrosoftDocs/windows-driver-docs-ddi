---
UID: NF:wdfdmatransaction.WdfDmaTransactionSetMaximumLength
title: WdfDmaTransactionSetMaximumLength function (wdfdmatransaction.h)
description: The WdfDmaTransactionSetMaximumLength method sets the maximum length for the DMA transfers that are associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactionsetmaximumlength.htm
tech.root: wdf
ms.assetid: b195c6df-79c4-427d-b722-309f43a4e150
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionSetMaximumLength function"]
ms.keywords: DFDmaObjectRef_966c396e-c161-46d6-856e-9bc9aa30c610.xml, WdfDmaTransactionSetMaximumLength, WdfDmaTransactionSetMaximumLength method, kmdf.wdfdmatransactionsetmaximumlength, wdf.wdfdmatransactionsetmaximumlength, wdfdmatransaction/WdfDmaTransactionSetMaximumLength
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionSetMaximumLength"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionSetMaximumLength
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionSetMaximumLength function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionSetMaximumLength</b> method sets the maximum length for the DMA transfers that are associated with a specified DMA transaction.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param MaximumLength [in]

The maximum size, in bytes, that the device can handle in a single DMA transfer operation. If your driver must run on versions of the Microsoft Windows operating systems that support a maximum of 16 <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/map-registers">map registers</a>, <i>MaximumLength</i> must be less than 65536.

The <i>MaximumLength</i> value applies only to the specified DMA transaction, as follows:

<ul>
<li>
If the specified value is less than the default value that the driver specified in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure, the specified value overrides the default value. 

</li>
<li>
If the specified value is greater than the default value, the specified value is ignored.

</li>
</ul>

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



Your driver  must initialize the DMA transaction before calling <b>WdfDmaTransactionSetMaximumLength</b>.

For information about initializing a DMA transaction, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-and-initializing-a-dma-transaction">Creating and Initializing a DMA Transaction</a>.


#### Examples

The following code example sets the maximum transfer length to a driver-defined value, for a specified DMA transaction.

```cpp
WdfDmaTransactionSetMaximumLength(
                                 dmaTransaction,
                                 MAX_TRANSFER_LENGTH/2,
                                 );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
 

 


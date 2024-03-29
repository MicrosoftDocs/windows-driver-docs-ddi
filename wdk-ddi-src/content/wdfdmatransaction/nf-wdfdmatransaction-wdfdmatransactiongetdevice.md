---
UID: NF:wdfdmatransaction.WdfDmaTransactionGetDevice
title: WdfDmaTransactionGetDevice function (wdfdmatransaction.h)
description: The WdfDmaTransactionGetDevice method returns a handle to the framework device object that is associated with a specified DMA transaction.
old-location: wdf\wdfdmatransactiongetdevice.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionGetDevice function"]
ms.keywords: DFDmaObjectRef_eb3ef52a-cba0-4754-8dad-d113b200f949.xml, WdfDmaTransactionGetDevice, WdfDmaTransactionGetDevice method, kmdf.wdfdmatransactiongetdevice, wdf.wdfdmatransactiongetdevice, wdfdmatransaction/WdfDmaTransactionGetDevice
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDmaTransactionGetDevice
 - wdfdmatransaction/WdfDmaTransactionGetDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfDmaTransactionGetDevice
---

# WdfDmaTransactionGetDevice function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDmaTransactionGetDevice</b> method returns a handle to the framework device object that is associated with a specified DMA transaction.

## -parameters

### -param DmaTransaction [in]


A handle to a DMA transaction object that the driver obtained from a previous call to <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.

## -returns

<b>WdfDmaTransactionGetDevice</b> returns a handle to the framework device object that the driver specified when it called <a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about completing DMA transfers, see <a href="/windows-hardware/drivers/wdf/completing-a-dma-transfer">Completing a DMA Transfer</a>. 


#### Examples

The following code example obtains a handle to the framework device object that is associated with a specified DMA transaction.

```cpp
WDFDEVICE device;

device = WdfDmaTransactionGetDevice(DmaTransaction);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>

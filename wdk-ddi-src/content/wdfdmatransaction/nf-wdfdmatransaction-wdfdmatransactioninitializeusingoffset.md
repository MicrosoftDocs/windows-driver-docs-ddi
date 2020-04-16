---
UID: NF:wdfdmatransaction.WdfDmaTransactionInitializeUsingOffset
title: WdfDmaTransactionInitializeUsingOffset function (wdfdmatransaction.h)
description: The WdfDmaTransactionInitializeUsingOffset method initializes a specified DMA transaction by using a byte offset into an MDL chain.
old-location: wdf\wdfdmatransactioninitializeusingoffset.htm
tech.root: wdf
ms.assetid: 896343A8-0C72-47D4-8465-A029EDCD66A0
ms.date: 02/26/2018
keywords: ["WdfDmaTransactionInitializeUsingOffset function"]
ms.keywords: WdfDmaTransactionInitializeUsingOffset, WdfDmaTransactionInitializeUsingOffset method, kmdf.wdfdmatransactioninitializeusingoffset, wdf.wdfdmatransactioninitializeusingoffset, wdfdmatransaction/WdfDmaTransactionInitializeUsingOffset
f1_keywords:
 - "wdfdmatransaction/WdfDmaTransactionInitializeUsingOffset"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDmaTransactionInitializeUsingOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDmaTransactionInitializeUsingOffset function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The 
   <b>WdfDmaTransactionInitializeUsingOffset</b> method initializes a specified DMA transaction by using a byte offset into an MDL chain.


## -parameters




### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.


### -param EvtProgramDmaFunction [in]

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nc-wdfdmatransaction-evt_wdf_program_dma">EvtProgramDma</a> event callback function. 


### -param DmaDirection [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ne-wdfdmaenabler-_wdf_dma_direction">WDF_DMA_DIRECTION</a>-typed value.


### -param Mdl [in]

A pointer to a memory descriptor list (MDL) that describes the buffer that will be used for the DMA transaction. See more information in <b>Remarks</b>.


### -param Offset [in]

The byte offset into the MDL chain for the current transaction.


### -param Length [in]

The number of bytes to be transferred. This value must be greater than zero.


## -returns



<b>WdfDmaTransactionInitializeUsingOffset</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, the method might return one of the values described in the Return values section of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>.

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



<b>WdfDmaTransactionInitializeUsingOffset</b> is equivalent to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a> except that it takes an offset into the buffer described by the MDL chain rather than a virtual address.

The driver can specify an MDL chain in the <i>Mdl</i> parameter of this method. An MDL chain is a sequence of MDL structures that the driver chained together using the <b>Next</b> member of the MDL structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactioninitialize">WdfDmaTransactionInitialize</a>
 

 


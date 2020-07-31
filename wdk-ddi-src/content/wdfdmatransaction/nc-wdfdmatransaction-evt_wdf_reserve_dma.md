---
UID: NC:wdfdmatransaction.EVT_WDF_RESERVE_DMA
title: EVT_WDF_RESERVE_DMA (wdfdmatransaction.h)
description: The EvtReserveDma event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.
old-location: wdf\evtreservedma.htm
tech.root: wdf
ms.assetid: 3663EF19-5F16-43D1-BFBC-28280E28D4DE
ms.date: 02/26/2018
keywords: ["EVT_WDF_RESERVE_DMA callback function"]
ms.keywords: EVT_WDF_RESERVE_DMA, EVT_WDF_RESERVE_DMA callback, EvtReserveDma, EvtReserveDma callback function, kmdf.evtreservedma, wdf.evtreservedma, wdfdmatransaction/EvtReserveDma
f1_keywords:
 - "wdfdmatransaction/EvtReserveDma"
 - "EvtReserveDma"
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfDmaTransaction.h
api_name:
- EvtReserveDma
targetos: Windows
req.typenames: 
---

# EVT_WDF_RESERVE_DMA callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <i>EvtReserveDma</i> event callback function is called when the framework has reserved resources to execute and release a transaction. Reserved resources include map registers and the WDM DMA adapter's lock.


## -parameters




### -param DmaTransaction [in]

A handle to the DMA transaction object that represents the transaction to which DMA resources were assigned.


### -param Context [in]

The context pointer that the driver specified in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>.


## -remarks



Drivers register an <i>EvtReserveDma</i> event callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>.

The framework calls a driver's <i>EvtReserveDma</i> event callback function when DMA resources have been assigned for exclusive use with the associated transaction object. The driver can initialize and execute the transaction multiple times while holding this reservation.

A driver typically initializes and then initiates the transaction from within its <i>EvtReserveDma</i> event callback function. For more information about the reservation sequence, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/reserving-dma-resources">Reserving DMA Resources</a>.

  

The driver may call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionfreeresources">WdfDmaTransactionFreeResources</a> from within <i>EvtReserveDma</i>.


On operating systems earlier than Windows 8, <i>EvtReserveDma</i> must be used with an enabler that specifies a packet-mode DMA enabler.  Starting with  Windows 8, <i>EvtReserveDma</i> can also be used with an enabler that specifies a system-mode DMA enabler.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionallocateresources">WdfDmaTransactionAllocateResources</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmatransaction/nf-wdfdmatransaction-wdfdmatransactionfreeresources">WdfDmaTransactionFreeResources</a>
 

 


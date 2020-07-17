---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_FLUSH
title: EVT_WDF_DMA_ENABLER_FLUSH (wdfdmaenabler.h)
description: A driver's EvtDmaEnablerFlush event callback function deallocates a device's DMA buffers.
old-location: wdf\evtdmaenablerflush.htm
tech.root: wdf
ms.assetid: bb606889-7d05-49a0-b0b7-e1f6d6c315d8
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_ENABLER_FLUSH callback function"]
ms.keywords: DFDmaObjectRef_0a019ec3-228e-47d0-ab8c-9c07e200e229.xml, EVT_WDF_DMA_ENABLER_FLUSH, EVT_WDF_DMA_ENABLER_FLUSH callback, EvtDmaEnablerFlush, EvtDmaEnablerFlush callback function, kmdf.evtdmaenablerflush, wdf.evtdmaenablerflush, wdfdmaenabler/EvtDmaEnablerFlush
f1_keywords:
 - "wdfdmaenabler/EvtDmaEnablerFlush"
 - "EvtDmaEnablerFlush"
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfDmaEnabler.h
api_name:
- EvtDmaEnablerFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DMA_ENABLER_FLUSH callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDmaEnablerFlush</i> event callback function deallocates a device's DMA buffers.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns



<i>EvtDmaEnablerFlush</i> must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



To register an <i>EvtDmaEnablerFlush</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerFlush</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-power-management-for-dma-devices">Supporting Power Management for DMA Devices</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_fill">EvtDmaEnablerFill</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>
 

 


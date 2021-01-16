---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
title: EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP (wdfdmaenabler.h)
description: A driver's EvtDmaEnablerSelfManagedIoStop event callback function stops a DMA device's self-managed I/O operations.
old-location: wdf\evtdmaenablerselfmanagediostop.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback function"]
ms.keywords: DFDmaObjectRef_b04ab1d3-dbff-42f2-b22a-a212d04fac5b.xml, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback, EvtDmaEnablerSelfManagedIoStop, EvtDmaEnablerSelfManagedIoStop callback function, kmdf.evtdmaenablerselfmanagediostop, wdf.evtdmaenablerselfmanagediostop, wdfdmaenabler/EvtDmaEnablerSelfManagedIoStop
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
 - wdfdmaenabler/EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfDmaEnabler.h
api_name:
 - EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP
---

# EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_STOP callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDmaEnablerSelfManagedIoStop</i> event callback function stops a DMA device's self-managed I/O operations.

## -parameters

### -param DmaEnabler 

[in]
A handle to a DMA enabler object.

## -returns

<i>EvtDmaEnablerSelfManagedIoStop</i> must return STATUS_SUCCESS or another status value for which <a href="/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## -remarks

To register an <i>EvtDmaEnablerSelfManagedIoStop</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerSelfManagedIoStop</i> callback function, see <a href="/windows-hardware/drivers/wdf/supporting-power-management-for-dma-devices">Supporting Power Management for DMA Devices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_start">EvtDmaEnablerSelfManagedIoStart</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>


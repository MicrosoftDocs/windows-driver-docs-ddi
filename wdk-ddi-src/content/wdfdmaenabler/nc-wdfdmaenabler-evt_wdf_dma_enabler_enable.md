---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_ENABLE
title: EVT_WDF_DMA_ENABLER_ENABLE (wdfdmaenabler.h)
description: A driver's EvtDmaEnablerEnable event callback function enables a device's DMA capability after the device enters its working (D0) state.
old-location: wdf\evtdmaenablerenable.htm
tech.root: wdf
ms.assetid: b6344a06-98ee-48c0-8fd5-76edfc71af2b
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_ENABLER_ENABLE callback function"]
ms.keywords: DFDmaObjectRef_ca81d643-d2a6-4f88-9c6e-80c5681b76d1.xml, EVT_WDF_DMA_ENABLER_ENABLE, EVT_WDF_DMA_ENABLER_ENABLE callback, EvtDmaEnablerEnable, EvtDmaEnablerEnable callback function, kmdf.evtdmaenablerenable, wdf.evtdmaenablerenable, wdfdmaenabler/EvtDmaEnablerEnable
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
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DMA_ENABLER_ENABLE
 - wdfdmaenabler/EVT_WDF_DMA_ENABLER_ENABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfDmaEnabler.h
api_name:
 - EvtDmaEnablerEnable
---

# EVT_WDF_DMA_ENABLER_ENABLE callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDmaEnablerEnable</i> event callback function enables a device's DMA capability after the device enters its working (D0) state.

## -parameters

### -param DmaEnabler 

[in]
A handle to a DMA enabler object.

## -returns

<i>EvtDmaEnablerEnable</i>  must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.

## -remarks

To register an <i>EvtDmaEnablerEnable</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerEnable</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-power-management-for-dma-devices">Supporting Power Management for DMA Devices</a>.

The <i>EvtDmaEnablerEnable</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_disable">EvtDmaEnablerDisable</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>


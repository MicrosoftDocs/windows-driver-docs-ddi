---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START
title: EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START (wdfdmaenabler.h)
description: A driver's EvtDmaEnablerSelfManagedIoStart event callback function starts a DMA device's self-managed I/O operations.
old-location: wdf\evtdmaenablerselfmanagediostart.htm
tech.root: wdf
ms.assetid: 397791c1-c394-48ae-b6cf-42f4494438f1
ms.date: 02/26/2018
keywords: ["EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback function"]
ms.keywords: DFDmaObjectRef_6ccb5cb2-c30f-4ae0-a47e-cb58e24de25b.xml, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback, EvtDmaEnablerSelfManagedIoStart, EvtDmaEnablerSelfManagedIoStart callback function, kmdf.evtdmaenablerselfmanagediostart, wdf.evtdmaenablerselfmanagediostart, wdfdmaenabler/EvtDmaEnablerSelfManagedIoStart
f1_keywords:
 - "wdfdmaenabler/EvtDmaEnablerSelfManagedIoStart"
 - "EvtDmaEnablerSelfManagedIoStart"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfDmaEnabler.h
api_name:
- EvtDmaEnablerSelfManagedIoStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDmaEnablerSelfManagedIoStart</i> event callback function starts a DMA device's self-managed I/O operations.


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns



<i>EvtDmaEnablerSelfManagedIoStart</i> must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



To register an <i>EvtDmaEnablerSelfManagedIoStart</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerSelfManagedIoStart</i> callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-power-management-for-dma-devices">Supporting Power Management for DMA Devices</a>.

The <i>EvtDmaEnablerSelfManagedIoStart</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop">EvtDmaEnablerSelfManagedIoStop</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/ns-wdfdmaenabler-_wdf_dma_enabler_config">WDF_DMA_ENABLER_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdmaenabler/nf-wdfdmaenabler-wdfdmaenablercreate">WdfDmaEnablerCreate</a>
 

 


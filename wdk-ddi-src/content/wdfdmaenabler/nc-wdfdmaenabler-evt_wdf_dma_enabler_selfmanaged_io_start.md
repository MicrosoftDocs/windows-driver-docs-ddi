---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START
title: EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START
author: windows-driver-content
description: A driver's EvtDmaEnablerSelfManagedIoStart event callback function starts a DMA device's self-managed I/O operations.
old-location: wdf\evtdmaenablerselfmanagediostart.htm
old-project: wdf
ms.assetid: 397791c1-c394-48ae-b6cf-42f4494438f1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmaenablerselfmanagediostart, EvtDmaEnablerSelfManagedIoStart callback function, EvtDmaEnablerSelfManagedIoStart, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START, EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START, wdfdmaenabler/EvtDmaEnablerSelfManagedIoStart, DFDmaObjectRef_6ccb5cb2-c30f-4ae0-a47e-cb58e24de25b.xml, kmdf.evtdmaenablerselfmanagediostart
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfDmaEnabler.h
apiname:
-	EvtDmaEnablerSelfManagedIoStart
product: Windows
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDmaEnablerSelfManagedIoStart</i> event callback function starts a DMA device's self-managed I/O operations.


## -prototype


````
EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START EvtDmaEnablerSelfManagedIoStart;

NTSTATUS EvtDmaEnablerSelfManagedIoStart(
  _In_ WDFDMAENABLER DmaEnabler
)
{ ... }
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns


<i>EvtDmaEnablerSelfManagedIoStart</i> must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 



## -remarks


To register an <i>EvtDmaEnablerSelfManagedIoStart</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerSelfManagedIoStart</i> callback function, see <a href="https://msdn.microsoft.com/abbb8f60-560f-41c9-85c5-1ec82078b99e">Supporting Power Management for DMA Devices</a>.

The <i>EvtDmaEnablerSelfManagedIoStart</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.



## -see-also

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_selfmanaged_io_stop.md">EvtDmaEnablerSelfManagedIoStop</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_ENABLER_SELFMANAGED_IO_START callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


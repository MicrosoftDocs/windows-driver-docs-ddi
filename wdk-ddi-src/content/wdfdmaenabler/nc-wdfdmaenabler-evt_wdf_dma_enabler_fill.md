---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_FILL
title: EVT_WDF_DMA_ENABLER_FILL
author: windows-driver-content
description: A driver's EvtDmaEnablerFill event callback function allocates a device's DMA buffers.
old-location: wdf\evtdmaenablerfill.htm
old-project: wdf
ms.assetid: 3da947b4-76f9-492f-b8e2-b52aa7812b26
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmaenablerfill, EvtDmaEnablerFill callback function, EvtDmaEnablerFill, EVT_WDF_DMA_ENABLER_FILL, EVT_WDF_DMA_ENABLER_FILL, wdfdmaenabler/EvtDmaEnablerFill, DFDmaObjectRef_3546c1f6-cb96-4b6e-bafa-25a1d15b00c5.xml, kmdf.evtdmaenablerfill
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
-	EvtDmaEnablerFill
product: Windows
targetos: Windows
req.typenames: WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_ENABLER_FILL callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDmaEnablerFill</i> event callback function allocates a device's DMA buffers.


## -prototype


````
EVT_WDF_DMA_ENABLER_FILL EvtDmaEnablerFill;

NTSTATUS EvtDmaEnablerFill(
  _In_ WDFDMAENABLER DmaEnabler
)
{ ... }
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns


<i>EvtDmaEnablerFill</i> must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 



## -remarks


To register an <i>EvtDmaEnablerFill</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerFill</i> callback function, see <a href="https://msdn.microsoft.com/abbb8f60-560f-41c9-85c5-1ec82078b99e">Supporting Power Management for DMA Devices</a>.

The <i>EvtDmaEnablerFill</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>

<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_flush.md">EvtDmaEnablerFlush</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_ENABLER_FILL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


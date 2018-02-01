---
UID: NC:wdfdmaenabler.EVT_WDF_DMA_ENABLER_DISABLE
title: EVT_WDF_DMA_ENABLER_DISABLE
author: windows-driver-content
description: A driver's EvtDmaEnablerDisable event callback function disables a device's DMA capability before the device leaves its working (D0) state.
old-location: wdf\evtdmaenablerdisable.htm
old-project: wdf
ms.assetid: 0a39e19b-9720-4641-83f0-654a5f116432
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdmaenablerdisable, EvtDmaEnablerDisable callback function, EvtDmaEnablerDisable, EVT_WDF_DMA_ENABLER_DISABLE, EVT_WDF_DMA_ENABLER_DISABLE, wdfdmaenabler/EvtDmaEnablerDisable, DFDmaObjectRef_f8cd455b-22a3-47d4-b430-a4e8139aa96e.xml, kmdf.evtdmaenablerdisable
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	WdfDmaEnabler.h
apiname:
-	EvtDmaEnablerDisable
product: Windows
targetos: Windows
req.typenames: "*PWDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS"
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_ENABLER_DISABLE callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtDmaEnablerDisable</i> event callback function disables a device's DMA capability before the device leaves its working (D0) state.


## -prototype


````
EVT_WDF_DMA_ENABLER_DISABLE EvtDmaEnablerDisable;

NTSTATUS EvtDmaEnablerDisable(
  _In_ WDFDMAENABLER DmaEnabler
)
{ ... }
````


## -parameters




### -param DmaEnabler [in]

A handle to a DMA enabler object.  


## -returns


<i>EvtDmaEnablerDisable</i> must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 



## -remarks


To register an <i>EvtDmaEnablerDisable</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.

For more information about the <i>EvtDmaEnablerDisable</i> callback function, see <a href="https://msdn.microsoft.com/abbb8f60-560f-41c9-85c5-1ec82078b99e">Supporting Power Management for DMA Devices</a>.



## -see-also

<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>

<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt_wdf_dma_enabler_enable.md">EvtDmaEnablerEnable</a>

<a href="..\wdfdmaenabler\ns-wdfdmaenabler-_wdf_dma_enabler_config.md">WDF_DMA_ENABLER_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_ENABLER_DISABLE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


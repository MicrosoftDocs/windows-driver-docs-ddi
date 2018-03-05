---
UID: NE:d3dkmddi._DXGK_INTERRUPT_TYPE
title: "_DXGK_INTERRUPT_TYPE"
author: windows-driver-content
description: The DXGK_INTERRUPT_TYPE enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about.
old-location: display\dxgk_interrupt_type.htm
old-project: display
ms.assetid: f942e448-94b8-400b-927b-fb5f2b1f544e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGK_INTERRUPT_CRTC_VSYNC, DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, DXGK_INTERRUPT_DISPLAYONLY_VSYNC, DXGK_INTERRUPT_DMA_COMPLETED, DXGK_INTERRUPT_DMA_FAULTED, DXGK_INTERRUPT_DMA_PAGE_FAULTED, DXGK_INTERRUPT_DMA_PREEMPTED, DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, DXGK_INTERRUPT_TYPE, DXGK_INTERRUPT_TYPE enumeration [Display Devices], DmEnums_5ed0a892-5813-43ff-aae9-25b03aa3ea5f.xml, _DXGK_INTERRUPT_TYPE, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_VSYNC, d3dkmddi/DXGK_INTERRUPT_DMA_COMPLETED, d3dkmddi/DXGK_INTERRUPT_DMA_FAULTED, d3dkmddi/DXGK_INTERRUPT_DMA_PAGE_FAULTED, d3dkmddi/DXGK_INTERRUPT_DMA_PREEMPTED, d3dkmddi/DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, d3dkmddi/DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, d3dkmddi/DXGK_INTERRUPT_TYPE, display.dxgk_interrupt_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_INTERRUPT_TYPE
product: Windows
targetos: Windows
req.typenames: DXGK_INTERRUPT_TYPE
---

# _DXGK_INTERRUPT_TYPE enumeration


## -description


The DXGK_INTERRUPT_TYPE enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about.


## -syntax


````
typedef enum _DXGK_INTERRUPT_TYPE { 
  DXGK_INTERRUPT_DMA_COMPLETED                       = 1,
  DXGK_INTERRUPT_DMA_PREEMPTED                       = 2,
  DXGK_INTERRUPT_CRTC_VSYNC                          = 3,
  DXGK_INTERRUPT_DMA_FAULTED                         = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
  DXGK_INTERRUPT_DISPLAYONLY_VSYNC                   = 5,
  DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS        = 6,
  DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY  = 7,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_M1)
  DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE      = 8,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
  DXGK_INTERRUPT_DMA_PAGE_FAULTED                    = 9,
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
  DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED   = 11
} DXGK_INTERRUPT_TYPE;
````


## -enum-fields




### -field DXGK_INTERRUPT_DMA_COMPLETED

A direct memory access (DMA) buffer is completed by using a fence identifier. The driver must supply the DMA buffer fence identifier in the <b>SubmissionFenceId</b> member of the <b>DmaCompleted</b> structure in the union that is contained in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function. This DMA buffer fence identifier was assigned during a call to the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function for the latest completed DMA buffer.


### -field DXGK_INTERRUPT_DMA_PREEMPTED

A preemption request is completed. The driver must supply the preemption fence identifier in the <b>PreemptionFenceId</b> member and the latest fence identifier that hardware completed (not preempted) in the <b>LastCompletedFenceId</b> member of the <b>DmaPreempted</b> structure in the union that is contained in the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.

The GPU scheduler determines that the graphics hardware preempted all of the commands between the preemption request and the submission with the latest fence identifier. 


### -field DXGK_INTERRUPT_CRTC_VSYNC

A scan out is completed. The driver must supply information in the <b>CrtcVsync</b> structure in the union that is contained in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function. 

The display miniport driver notifies with this interrupt type after video hardware entered into the vertical retrace period, and the pending flip address was latched into the DAC and scanned out. The display miniport driver is not required to report this interrupt after the operating system calls the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a> function to disable the interrupt type; however, the driver must resume reporting after the operating system calls the driver's <i>DxgkDdiControlInterrupt</i> function again to enable the interrupt type. 


### -field DXGK_INTERRUPT_DMA_FAULTED

Reserved for system use. Do not use in your driver.


### -field DXGK_INTERRUPT_DISPLAYONLY_VSYNC

In a kernel mode display-only driver, a VSync has completed.

Supported starting with Windows 8.


### -field DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS

In a kernel mode display-only driver, a present operation has completed or has failed.

Supported starting with Windows 8.


### -field DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY

A Vsync has completed in a display miniport driver that supports multiplane overlays.

Supported starting with Windows 8.1.


### -field DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE


### -field DXGK_INTERRUPT_DMA_PAGE_FAULTED

This interrupt type should be raised when a GPU encounters an error condition that requires OS to perform a recovery action, such as putting the running packet device in error or resetting the GPU.


When this interrupt type is set, interrupt data should be provided in the <b>DmaPageFaulted</b> member of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a> structure.

Supported starting with Windows 10.


### -field DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY2


### -field DXGK_INTERRUPT_MONITORED_FENCE_SIGNALED


### -field DXGK_INTERRUPT_HWQUEUE_PAGE_FAULTED


### -field DXGK_INTERRUPT_HWCONTEXTLIST_SWITCH_COMPLETED


### -field DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED

This interrupt type should be raised when the periodic monitored fence is signaled. 

Supported starting with Windows 10.


#### - DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE

The GPU has completed encoding a Miracast encode chunk.

The display miniport driver can optionally provide private data that the user-mode driver can obtain using the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>  function.

Supported starting with Windows 8.1.


## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_get_next_chunk_data.md">GetNextChunkData</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md">DXGKARGCB_NOTIFY_INTERRUPT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_INTERRUPT_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


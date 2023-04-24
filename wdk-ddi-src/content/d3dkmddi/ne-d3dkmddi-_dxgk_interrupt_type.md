---
UID: NE:d3dkmddi._DXGK_INTERRUPT_TYPE
title: DXGK_INTERRUPT_TYPE (d3dkmddi.h)
description: Learn more about the DXGK_INTERRUPT_TYPE enumeration.
old-location: display\dxgk_interrupt_type.htm
ms.date: 02/03/2023
ms.keywords: DXGK_INTERRUPT_CRTC_VSYNC, DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, DXGK_INTERRUPT_DISPLAYONLY_VSYNC, DXGK_INTERRUPT_DMA_COMPLETED, DXGK_INTERRUPT_DMA_FAULTED, DXGK_INTERRUPT_DMA_PAGE_FAULTED, DXGK_INTERRUPT_DMA_PREEMPTED, DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, DXGK_INTERRUPT_TYPE, DXGK_INTERRUPT_TYPE enumeration [Display Devices], DmEnums_5ed0a892-5813-43ff-aae9-25b03aa3ea5f.xml, _DXGK_INTERRUPT_TYPE, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC, d3dkmddi/DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS, d3dkmddi/DXGK_INTERRUPT_DISPLAYONLY_VSYNC, d3dkmddi/DXGK_INTERRUPT_DMA_COMPLETED, d3dkmddi/DXGK_INTERRUPT_DMA_FAULTED, d3dkmddi/DXGK_INTERRUPT_DMA_PAGE_FAULTED, d3dkmddi/DXGK_INTERRUPT_DMA_PREEMPTED, d3dkmddi/DXGK_INTERRUPT_MICACAST_ENCODE_CHUNK_COMPLETE, d3dkmddi/DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED, d3dkmddi/DXGK_INTERRUPT_TYPE, display.dxgk_interrupt_type
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
targetos: Windows
tech.root: display
req.typenames: DXGK_INTERRUPT_TYPE
f1_keywords:
 - _DXGK_INTERRUPT_TYPE
 - d3dkmddi/_DXGK_INTERRUPT_TYPE
 - DXGK_INTERRUPT_TYPE
 - d3dkmddi/DXGK_INTERRUPT_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_INTERRUPT_TYPE
 - DXGK_INTERRUPT_TYPE
---

# DXGK_INTERRUPT_TYPE enumeration

## -description

The **DXGK_INTERRUPT_TYPE** enumeration indicates the type of interrupt that the display miniport driver notifies the graphics processing unit (GPU) scheduler about.

## -enum-fields

### -field DXGK_INTERRUPT_DMA_COMPLETED:1

A direct memory access (DMA) buffer is completed by using a fence identifier. The driver must supply the DMA buffer fence identifier in the **SubmissionFenceId** member of the **DmaCompleted** structure in the union that is contained in the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure in a call to the [**DxgkCbNotifyInterrupt**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function. This DMA buffer fence identifier was assigned during a call to the driver's [**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) function for the latest completed DMA buffer.

### -field DXGK_INTERRUPT_DMA_PREEMPTED:2

A preemption request is completed. The driver must supply the preemption fence identifier in the **PreemptionFenceId** member and the latest fence identifier that hardware completed (not preempted) in the **LastCompletedFenceId** member of the **DmaPreempted** structure in the union that is contained in the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure in a call to the [**DxgkCbNotifyInterrupt**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

The GPU scheduler determines that the graphics hardware preempted all of the commands between the preemption request and the submission with the latest fence identifier.

### -field DXGK_INTERRUPT_CRTC_VSYNC:3

A scan out is completed. The driver must supply information in the **CrtcVsync** structure in the union that is contained in the [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure in a call to the [**DxgkCbNotifyInterrupt**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

The display miniport driver notifies with this interrupt type after video hardware entered into the vertical retrace period, and the pending flip address was latched into the DAC and scanned out. The display miniport driver is not required to report this interrupt after the operating system calls the driver's [**DxgkDdiControlInterrupt**](nc-d3dkmddi-dxgkddi_controlinterrupt.md) function to disable the interrupt type; however, the driver must resume reporting after the operating system calls the driver's *DxgkDdiControlInterrupt* function again to enable the interrupt type.

### -field DXGK_INTERRUPT_DMA_FAULTED:4

Reserved for system use. Do not use in your driver.

### -field DXGK_INTERRUPT_DISPLAYONLY_VSYNC:5

In a kernel-mode display-only driver, a VSync has completed. Supported starting with Windows 8.

### -field DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS:6

In a kernel-mode display-only driver, a present operation has completed or has failed. Supported starting with Windows 8.

### -field DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY:7

A Vsync has completed in a display miniport driver that supports multiplane overlays. Supported starting with Windows 8.1.

### -field DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE:8

The GPU has completed encoding a Miracast encode chunk. Supported starting with Windows 8.1.

The display miniport driver can optionally provide private data that the user-mode driver can obtain using the [**GetNextChunkData**](../netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data.md)  function.

### -field DXGK_INTERRUPT_DMA_PAGE_FAULTED:9

This interrupt type should be raised when a GPU encounters an error condition that requires OS to perform a recovery action, such as putting the running packet device in error or resetting the GPU. Supported starting with Windows 10.

When this interrupt type is set, interrupt data should be provided in the **DmaPageFaulted** member of [**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md) structure.

### -field DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY2:10

A Vsync has completed in a display miniport driver that supports multiplane overlays. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_MONITORED_FENCE_SIGNALED:11

Raise this interrupt type when the monitored fence is signaled. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_HWQUEUE_PAGE_FAULTED:12

Raise this interrupt type when the hardware queue page has faulted. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_HWCONTEXTLIST_SWITCH_COMPLETED:13

Raise this interrupt type when the hardware context list switch has completed. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED:14

Raise this interrupt type when the periodic monitored fence is signaled. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_SCHEDULING_LOG_INTERRUPT:15

Raised during a scheduling log interrupt. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_GPU_ENGINE_TIMEOUT:16

Raised when the GPU engine has timed out. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_SUSPEND_CONTEXT_COMPLETED:17

Raised when the suspend context has completed. Supported starting with Windows 10.

### -field DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY3:18

A Vsync has completed in a display miniport driver that supports the [hardware flip queue model](/windows-hardware/drivers/display/hardware-flip-queue). Supported starting with Windows 11 (WDDM 3.0).

### -field DXGK_INTERRUPT_NATIVE_FENCE_SIGNALED:19

Available starting in Windows 11, version 22H2 (WDDM 3.1).

### -field DXGK_INTERRUPT_GPU_ENGINE_STATE_CHANGE:20

Available starting in Windows 11, version 22H2 (WDDM 3.1).

## -see-also

[**DXGK_INTERRUPT_STATE**](ne-d3dkmddi-_dxgk_interrupt_state.md)

[**DXGKARG_CONTROLINTERRUPT2**](ns-d3dkmddi-_dxgkarg_controlinterrupt2.md)

[**DXGKARG_CONTROLINTERRUPT3**](ns-d3dkmddi-dxgkarg_controlinterrupt3.md)

[**DXGKARGCB_NOTIFY_INTERRUPT_DATA**](ns-d3dkmddi-_dxgkargcb_notify_interrupt_data.md)

[**DxgkCbNotifyInterrupt**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[**DxgkDdiControlInterrupt**](nc-d3dkmddi-dxgkddi_controlinterrupt.md)

[**DxgkDdi_ControlInterrupt2**](nc-d3dkmddi-dxgkddi_controlinterrupt2.md)

[**DxgkDdi_ControlInterrupt3**](nc-d3dkmddi-dxgkddi_controlinterrupt3.md)

[**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md)

[**GetNextChunkData**](../netdispumdddi/nc-netdispumdddi-pfn_get_next_chunk_data.md)

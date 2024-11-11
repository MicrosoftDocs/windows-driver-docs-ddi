---
UID: NS:d3dkmddi._DXGKARGCB_NOTIFY_INTERRUPT_DATA
title: DXGKARGCB_NOTIFY_INTERRUPT_DATA (d3dkmddi.h)
description: Learn more about the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure.
ms.date: 11/08/2024
keywords: ["DXGKARGCB_NOTIFY_INTERRUPT_DATA structure"]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista (WDDM 1.0)
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
req.typenames: DXGKARGCB_NOTIFY_INTERRUPT_DATA
f1_keywords:
 - _DXGKARGCB_NOTIFY_INTERRUPT_DATA
 - d3dkmddi/_DXGKARGCB_NOTIFY_INTERRUPT_DATA
 - DXGKARGCB_NOTIFY_INTERRUPT_DATA
 - d3dkmddi/DXGKARGCB_NOTIFY_INTERRUPT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_NOTIFY_INTERRUPT_DATA
 - DXGKARGCB_NOTIFY_INTERRUPT_DATA
---

# DXGKARGCB_NOTIFY_INTERRUPT_DATA structure

## -description

The **DXGKARGCB_NOTIFY_INTERRUPT_DATA** structure contains interrupt notification information for the [**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) callback function.

## -struct-fields

### -field InterruptType

A [**DXGK_INTERRUPT_TYPE**](ne-d3dkmddi-_dxgk_interrupt_type.md)-typed value that indicates the type of interrupt the display miniport driver is notifying the GPU scheduler about.

### -field DmaCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_COMPLETED**.

### -field DmaCompleted.SubmissionFenceId

The DMA buffer fence identifier of the completed command. This identifier was assigned during a call to the driver's [**DXGKDDI_SUBMITCOMMAND**](./nc-d3dkmddi-dxgkddi_submitcommand.md) function for the latest completed DMA buffer.

### -field DmaCompleted.NodeOrdinal

The zero-based index of the node that generates the notification.

### -field DmaCompleted.EngineOrdinal

The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to.

### -field DmaPreempted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_PREEMPTED**.

### -field DmaPreempted.PreemptionFenceId

The submission identifier of the preempting request.

### -field DmaPreempted.LastCompletedFenceId

The submission identifier of the last completed command before preemption.

### -field DmaPreempted.NodeOrdinal

The zero-based index of the node that generates the notification.

### -field DmaPreempted.EngineOrdinal

The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** set to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to. The GPU scheduler determines that hardware preempted all commands between the preemption request and the submission that **LastCompletedFenceId** specifies.

### -field DmaFaulted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_FAULTED**.

### -field DmaFaulted.FaultedFenceId

The identifier of the faulty command.

### -field DmaFaulted.Status

The status of the faulty command.

### -field DmaFaulted.NodeOrdinal

The zero-based index of the node that generates the notification.

### -field DmaFaulted.EngineOrdinal

The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to.

### -field CrtcVsync

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC**.

### -field CrtcVsync.VidPnTargetId

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.

### -field CrtcVsync.PhysicalAddress

The physical address of the displaying buffer. When monitor visibility is off, the operating system still expects a non-**NULL** physical address. This address should be set to the physical address that the pixel pipeline would read from if visibility were on.

### -field CrtcVsync.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member.

### -field DisplayOnlyVsync

Structure used when **InterruptType** is **DXGK_INTERRUPT_DISPLAYONLY_VSYNC**. Supported starting with Windows 8.

### -field DisplayOnlyVsync.VidPnTargetId

For a display-only driver, the zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY**. Provides VSync notifications for display miniport drivers that support multiplane overlays. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.VidPnTargetId

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.pMultiPlaneOverlayVsyncInfo

A pointer to a [**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO**](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md) structure that specifies an overlay plane to display during a VSync interval. Supported starting with Windows 8.

### -field DisplayOnlyPresentProgress

A [**DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS**](./ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md) structure that provides the progress of a kernel mode display-only driver's (KMDOD) present operation. Used when **InterruptType** is **DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS**. Supported starting with Windows 8.

### -field MiracastEncodeChunkCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE**. Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.

### -field MiracastEncodeChunkCompleted.VidPnTargetId

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the encoding is being performed. Supported starting with Windows 8.1.

### -field MiracastEncodeChunkCompleted.ChunkInfo

A [**DXGK_MIRACAST_CHUNK_INFO**](..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md) encode chunk information structure that the display miniport driver wants to report. Supported starting with Windows 8.1.

### -field MiracastEncodeChunkCompleted.pPrivateDriverData

A pointer to a block of private data that describes this encode chunk. Supported starting with Windows 8.1.

### -field MiracastEncodeChunkCompleted.PrivateDataDriverSize

The size, in bytes, of the block of private data in **pPrivateDriverData**.
This value must not be larger than the **MaxChunkPrivateDriverDataSize** value that the driver reported in the [**DXGK_MIRACAST_CAPS**](..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md) structure. Supported starting with Windows 8.1.

### -field MiracastEncodeChunkCompleted.Status

A value of type **NTSTATUS** that indicates whether the encode chunk was successfully added to the queue of chunks. If successful, **STATUS_SUCCESS** is returned. If any other value is returned, the chunk could not be added to the queue, and all outstanding chunks will be lost. Supported starting with Windows 8.1.

|Value|Meaning|
|--- |--- |
|STATUS_SUCCESS|The chunk was successfully added to the queue.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_NO_MEMORY|The interrupt-service-routine (ISR) ran out of free encode chunks.|

### -field DmaPageFaulted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_PAGE_FAULTED**. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedFenceId

Submission fence ID of faulted command.

If the faulted fence cannot be determined reliably, **PageFaultFlags** should have **DXGK_PAGE_FAULT_FENCE_INVALID** bit set, and **FaultedFenceId** should be set to 0. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedPrimitiveAPISequenceNumber

 When per draw fence write is enabled, this identifies the draw operation that caused the page fault, or **DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN** if such information is not available. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedPipelineStage

Render pipeline stage during which the fault was generated, or **DXGK_RENDER_PIPELINE_STAGE_UNKNOWN** if such information is not available. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedBindTableEntry

A bind table index of a resource being accessed at the time of the fault, or **DXGK_BIND_TABLE_ENTRY_UNKNOWN** if such information is not available. Supported starting with Windows 10.

### -field DmaPageFaulted.PageFaultFlags

Flags described in [**DXGK_PAGE_FAULT_FLAGS**](..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md) enumeration specifying the nature of the fault. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedVirtualAddress

GPU virtual address of fault, or **D3DGPU_NULL** if the fault has another cause. In the latter case, **FaultErrorCode** field should be used to describe the GPU error. Supported starting with Windows 10.

### -field DmaPageFaulted.NodeOrdinal

Node ordinal of the engine generating the notification. Supported starting with Windows 10.

### -field DmaPageFaulted.EngineOrdinal

Engine ordinal of the engine generating the notification. Supported starting with Windows 10.

### -field DmaPageFaulted.PageTableLevel

Describes page table level that the faulting operation was attempted on. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultErrorCode

A [**DXGK_FAULT_ERROR_CODE**](..\d3dkmdt\ns-d3dkmdt-_dxgk_fault_error_code.md) structure describing the error. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedProcessHandle

DirectX graphics kernel process handle of the process that generated page fault, or **NULL** if the faulted process cannot be determined. Supported starting with Windows 10.

### -field CrtcVsyncWithMultiPlaneOverlay2

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY2**. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.VidPnTargetId

Vsync with multiplane overlay Vidpn target id. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.pMultiPlaneOverlayVsyncInfo

A pointer to a [**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2**](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info2.md) structure that specifies information for each overlay plane updated by the VSync. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.GpuFrequency

The frequency of the GPU clock counter. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.GpuClockCounter

The GPU clock counter at the time of the VSYNC interrupt. Combined with GpuFrequency, this indicates the time of the VSYNC interrupt. Supported starting with Windows 10, version 1607.

### -field MonitoredFenceSignaled

Structure used when **InterruptType** is **DXGK_INTERRUPT_MONITORED_FENCE_SIGNALED**. Supported starting with Windows 10, version 1703.

### -field MonitoredFenceSignaled.NodeOrdinal

Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field MonitoredFenceSignaled.EngineOrdinal

Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_HWCONTEXTLIST_SWITCH_COMPLETED**. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.NodeOrdinal

Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.EngineOrdinal

Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.ContextSwitchFence

Context switch fence used to perform this switch operation. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted

Structure used when **InterruptType** is **DXGK_INTERRUPT_HWQUEUE_PAGE_FAULTED**. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedFenceId

HW queue progress fence ID of the faulted command. If the faulted fence could not be determined reliably PageFaultFlags should have DXGK_PAGE_FAULT_FENCE_INVALID flag set. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedVirtualAddress

Virtual address of fault, or 0 if the fault has another cause. In the latter case, FaultErrorCode field should be used to describe the GPU error. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedPrimitiveAPISequenceNumber

When per draw fence write is enabled, identifies the draw that caused the page fault, or DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedHwQueue

When DXGK_PAGE_FAULT_FENCE_INVALID is not set, specifies the handle of the HW queue that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedHwContext

When DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_HW_CONTEXT_VALID are set, specifies the handle of the HW context that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedProcessHandle

Wen DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_PROCESS_HANDLE_VALID are set, specifies the handle of the process that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.NodeOrdinal

Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.EngineOrdinal

Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedPipelineStage

Render pipeline stage during which the fault was generated, or DXGK_RENDER_PIPELINE_STAGE_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedBindTableEntry

A bind table index of a resource being accessed at the time of the fault, or DXGK_BIND_TABLE_ENTRY_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.PageFaultFlags

Flags specifying the nature of the page fault and recovery policy. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.PageTableLevel

Described page table level which the faulting operation was attempted on. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultErrorCode

Structure that contains error code describing the fault. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled

Structure used when **InterruptType** is **DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED**. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled.VidPnTargetId

The display signaling the monitored fence. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled.NotificationID

The notification id as multiple can be attached to one VidPnSource. Supported starting with Windows 10, version 1703.

### -field SchedulingLogInterrupt

Structure used when **InterruptType** is **DXGK_INTERRUPT_SCHEDULING_LOG_INTERRUPT**. Supported starting with Windows 10, version 1803.

### -field SchedulingLogInterrupt.NodeOrdinal

Node ordinal of engine that raised the scheduling log interrupt. Supported starting with Windows 10, version 1803.

### -field SchedulingLogInterrupt.EngineOrdinal

Engine ordinal of engine that raised the scheduling log interrupt. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout

Structure used when **InterruptType** is **DXGK_INTERRUPT_GPU_ENGINE_TIMEOUT**. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout.NodeOrdinal

Node ordinal of engine that timed out and needs the reset. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout.EngineOrdinal

Engine ordinal of engine that timed out and needs the reset. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_SUSPEND_CONTEXT_COMPLETED**. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted.hContext

Hardware context that the suspend acknowledgment is for. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted.ContextSuspendFence

Context suspend fence. Supported starting with Windows 10, version 1803.

### -field CrtcVsyncWithMultiPlaneOverlay3

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY3**. Available starting with Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.VidPnTargetId

Vsync with multiplane overlay Vidpn target id. Available starting with Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member. Available starting in Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.MultiPlaneOverlayVsyncInfoCount

The number of [**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3**](ns-d3dkmddi-dxgk_multiplane_overlay_vsync_info3.md) structures that **CrtcVsyncWithMultiPlaneOverlay3.pMultiPlaneOverlayVsyncInfo** points to. These structures describe the overlay planes that are available to display. Available starting in Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.pMultiPlaneOverlayVsyncInfo

A pointer to an array of [**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO3**](ns-d3dkmddi-dxgk_multiplane_overlay_vsync_info3.md) structures that specify information for each overlay plane updated by the VSync. See [Hardware flip queue](/windows-hardware/drivers/display/hardware-flip-queue) for more information. Available starting in Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.GpuFrequency

The frequency of the GPU clock counter. Available starting in Windows Server 2022 (WDDM 2.9).

### -field CrtcVsyncWithMultiPlaneOverlay3.GpuClockCounter

The GPU clock counter at the time of the VSYNC interrupt. Combined with GpuFrequency, this indicates the time of the VSYNC interrupt. Available starting in Windows Server 2022 (WDDM 2.9).

### -field NativeFenceSignaled

[in] Structure used when [**InterruptType**](ne-d3dkmddi-_dxgk_interrupt_type.md) is **DXGK_INTERRUPT_NATIVE_FENCE_SIGNALED**. For more information about native fences, see [Native GPU fence objects](/windows-hardware/drivers/display/native-gpu-fence-objects). Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field NativeFenceSignaled.NodeOrdinal

Node ordinal of the engine generating the notification. Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field NativeFenceSignaled.EngineOrdinal

Engine ordinal of the engine generating the notification. Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field NativeFenceSignaled.SignaledNativeFenceCount

The size of the signaled native fence array that **pSignaledNativeFenceArray** points to. Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field NativeFenceSignaled.pSignaledNativeFenceArray

Array containing OS kernel-mode handles of all native fences that were signaled and require waiters to be unblocked. If this array is empty, the OS will rescan all pending native fence waiters instead of the subset specified by the signaled native fence array. *Dxgkrnl* reads this value only if [**DXGK_VIDSCHCAPS::OptimizedNativeFenceInterrupt**](ns-d3dkmddi-_dxgk_vidschcaps.md) is FALSE. Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field NativeFenceSignaled.hHWQueue

KMD handle of the HWQueue running on the engine that raised the interrupt. If this handle is NULL then *Dxgkrnl* will re-scan the log buffer of all HWQueues on this engine. *Dxgkrnl* reads this value only if [**DXGK_VIDSCHCAPS::OptimizedNativeFenceInterrupt**](ns-d3dkmddi-_dxgk_vidschcaps.md) is TRUE. Supported starting with Windows 11, version 24H2 (WDDM 3.2).

### -field EngineStateChange

[in] Structure used when **InterruptType** is **DXGK_INTERRUPT_GPU_ENGINE_STATE_CHANGE**. For more information, see [User-mode work submission](/windows-hardware/drivers/display/user-mode-work-submission). Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field EngineStateChange.NodeOrdinal

Node ordinal of the engine whose state changed. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field EngineStateChange.EngineOrdinal

Engine ordinal of the engine whose state changed. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field EngineStateChange.NewState

A [**DXGK_ENGINE_STATE**](ne-d3dkmddi-dxgk_engine_state.md) value that specifies the new state of the engine. Available starting with Windows 11, version 24H2 (WDDM 3.2).

### -field Reserved

Reserved for future use.

### -field Reserved.Reserved

An array of 32-bit values that are reserved for future use.

### -field Flags

A [**DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS**](ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md) structure that indicates whether the display miniport driver provides a physical adapter mask in a call to the [**DxgkCbNotifyInterrupt**](nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

## -remarks

A miniport driver fills in **DXGKARGCB_NOTIFY_INTERRUPT_DATA**, and then uses the [**DXGKCB_SYNCHRONIZE_EXECUTION**](../dispmprt/nc-dispmprt-dxgkcb_synchronize_execution.md) callback to sync with the interrupt. The **SynchronizeRoutine** parameter of the **DXGKCB_SYNCHRONIZE_EXECUTION** callback points to a miniport-implemented function that gets called by the OS when appropriate, and then the driver fills out the parameter info before calling back into the OS with the [**DXGKCB_NOTIFY_INTERRUPT**](./nc-d3dkmddi-dxgkcb_notify_interrupt.md) callback. The OS then handles the interrupt, with the scheduler using information in the DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 struct.

Depending on the value in the **InterruptType** member, the display miniport driver should set the appropriate union member in this structure. For example, for the end of a direct memory access (DMA) buffer fence, which corresponds to a value of DXGK_INTERRUPT_DMA_COMPLETED in **InterruptType**, the driver must set a value in the **SubmissionFenceId** member of the **DmaCompleted** member. This value should be the DMA buffer fence identifier, which the driver's [**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md) function assigned to the just completed DMA buffer.

## -see-also

[**DXGK_INTERRUPT_TYPE**](ne-d3dkmddi-_dxgk_interrupt_type.md)

[**DXGK_MIRACAST_CAPS**](..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md)

[**DXGK_MIRACAST_CHUNK_INFO**](..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md)

[**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO**](ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md)

[**DXGKCB_NOTIFY_INTERRUPT**](nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[**DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS**](ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md)

[**DXGK_PAGE_FAULT_FLAGS**](..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md)

[**DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS**](ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md)

[**DxgkDdiSubmitCommand**](nc-d3dkmddi-dxgkddi_submitcommand.md)

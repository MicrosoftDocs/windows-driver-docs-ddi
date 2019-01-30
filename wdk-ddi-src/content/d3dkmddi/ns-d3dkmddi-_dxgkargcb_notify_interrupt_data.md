---
UID: NS:d3dkmddi._DXGKARGCB_NOTIFY_INTERRUPT_DATA
title: "_DXGKARGCB_NOTIFY_INTERRUPT_DATA" (d3dkmddi.h)
description: The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information.
old-location: display\dxgkargcb_notify_interrupt_data.htm

ms.assetid: c71078fb-5666-4038-81a0-de9375bafb5c
ms.date: 04/16/2018
ms.keywords: "*IN_CONST_PDXGKARGCB_NOTIFY_INTERRUPT_DATA, DXGKARGCB_NOTIFY_INTERRUPT_DATA, DXGKARGCB_NOTIFY_INTERRUPT_DATA structure [Display Devices], DmStructs_071ed85c-70d6-44d8-95e3-7f6609331f4f.xml, STATUS_INVALID_PARAMETER, STATUS_NO_MEMORY, STATUS_SUCCESS, _DXGKARGCB_NOTIFY_INTERRUPT_DATA, d3dkmddi/DXGKARGCB_NOTIFY_INTERRUPT_DATA, display.dxgkargcb_notify_interrupt_data"
ms.topic: struct
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
-	DXGKARGCB_NOTIFY_INTERRUPT_DATA
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_NOTIFY_INTERRUPT_DATA
---

# _DXGKARGCB_NOTIFY_INTERRUPT_DATA structure


## -description


The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information.


## -syntax


```cpp
typedef struct _DXGKARGCB_NOTIFY_INTERRUPT_DATA {
  DXGK_INTERRUPT_TYPE                InterruptType;
  union {
    struct {
      UINT SubmissionFenceId;
      UINT NodeOrdinal;
      UINT EngineOrdinal;
    } DmaCompleted;
    struct {
      UINT PreemptionFenceId;
      UINT LastCompletedFenceId;
      UINT NodeOrdinal;
      UINT EngineOrdinal;
    } DmaPreempted;
    struct {
      UINT     FaultedFenceId;
      NTSTATUS Status;
      UINT     NodeOrdinal;
      UINT     EngineOrdinal;
    } DmaFaulted;
    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
      PHYSICAL_ADDRESS               PhysicalAddress;
      UINT                           PhysicalAdapterMask;
    } CrtcVsync;
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WIN8)
    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
    } DisplayOnlyVsync;
    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID     VidPnTargetId;
      UINT                               PhysicalAdapterMask;
      UINT                               MultiPlaneOverlayVsyncInfoCount;
      DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO *pMultiPlaneOverlayVsyncInfo;
    } CrtcVsyncWithMultiPlaneOverlay;
    DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS DisplayOnlyPresentProgress;
#endif

    struct {
      UINT Reserved[16];
    } Reserved;
  };
  DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS Flags;
} DXGKARGCB_NOTIFY_INTERRUPT_DATA;
```


## -struct-fields




### -field InterruptType

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>-typed value that indicates the type of interrupt that the display miniport driver notifies the GPU scheduler about.


### -field DmaCompleted

Structure of the completed display miniport adapter.

### -field DmaCompleted.SubmissionFenceId

[in] The submission identifier of the completed command.


### -field DmaCompleted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.


### -field DmaCompleted.EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set <b>EngineOrdinal</b> to 0. For graphics adapters that are part of a link, set <b>EngineOrdinal</b> to the adapter index of the adapter in the link that the interrupting engine belongs to.


### -field DmaPreempted

Structure of the display miniport adapter preempted.

### -field DmaPreempted.PreemptionFenceId

[in] The submission identifier of the preempting request.


### -field DmaPreempted.LastCompletedFenceId

[in] The submission identifier of the last completed command before preemption.


### -field DmaPreempted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.


### -field DmaPreempted.EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set <b>EngineOrdinal</b> set to 0. For graphics adapters that are part of a link, set <b>EngineOrdinal</b> to the adapter index of the adapter in the link that the interrupting engine belongs to. The GPU scheduler determines that hardware preempted all commands between the preemption request and the submission that <b>LastCompletedFenceId</b> specifies.


### -field DmaFaulted

Faulted.

### -field DmaFaulted.FaultedFenceId

[in] The identifier of the faulty command.


### -field DmaFaulted.Status

[in] The status of the faulty command.


### -field DmaFaulted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.


### -field DmaFaulted.EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set <b>EngineOrdinal</b> to 0. For graphics adapters that are part of a link, set <b>EngineOrdinal</b> to the adapter index of the adapter in the link that the interrupting engine belongs to.


### -field CrtcVsync


### -field CrtcVsync.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.


### -field CrtcVsync.PhysicalAddress

[in] The physical address of the displaying buffer. When monitor visibility is off, the operating system still expects a non-<b>NULL</b> physical address. This address should be set to the physical address that the pixel pipeline would read from if visibility were on.


### -field CrtcVsync.PhysicalAdapterMask

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the <b>ValidPhysicalAdapterMask</b> bit-field flag in the <b>Flags</b> member.


### -field DisplayOnlyVsync

When Vsync occurs.

### -field DisplayOnlyVsync.VidPnTargetId

[in] For a display-only driver, the zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.

Supported starting with Windows 8.


### -field CrtcVsyncWithMultiPlaneOverlay

Provides VSync notifications for display miniport drivers that support multiplane overlays.


### -field CrtcVsyncWithMultiPlaneOverlay.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.

Supported starting with Windows 8.1.


### -field CrtcVsyncWithMultiPlaneOverlay.PhysicalAdapterMask

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the <b>ValidPhysicalAdapterMask</b> bit-field flag in the <b>Flags</b> member.

Supported starting with Windows 8.1.


### -field CrtcVsyncWithMultiPlaneOverlay.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display.

Supported starting with Windows 8.1.


### -field CrtcVsyncWithMultiPlaneOverlay.pMultiPlaneOverlayVsyncInfo

[in] A pointer to  a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md">DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO</a> structure that specifies an overlay plane to display during a VSync interval.

Supported starting with Windows 8.1.


### -field DisplayOnlyPresentProgress

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/hh451245">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a> structure that provides the progress of a kernel mode display-only driver's (KMDOD) present operation.

Supported starting with Windows 8.


### -field MiracastEncodeChunkCompleted

Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.


### -field MiracastEncodeChunkCompleted.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the encoding is being performed.

Supported starting with Windows 8.1.


### -field MiracastEncodeChunkCompleted.ChunkInfo

A <a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md">DXGK_MIRACAST_CHUNK_INFO</a> encode chunk information structure that the display miniport driver wants to report.

Supported starting with Windows 8.1.


### -field MiracastEncodeChunkCompleted.pPrivateDriverData

A pointer to a block of private data that describes this encode chunk.

Supported starting with Windows 8.1.


### -field MiracastEncodeChunkCompleted.PrivateDataDriverSize

The size, in bytes, of the block of private data in <b>pPrivateDriverData</b>.
This value must not be larger than the <b>MaxChunkPrivateDriverDataSize</b> value that the driver reported in the <a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md">DXGK_MIRACAST_CAPS</a> structure.

Supported starting with Windows 8.1.


### -field MiracastEncodeChunkCompleted.Status

A value of type <b>NTSTATUS</b> that indicates whether the encode chunk was successfully added to the queue of chunks. If successful, <b>STATUS_SUCCESS</b> is returned. If any other value is returned, the chunk could not be added to the queue, and all outstanding chunks will be lost.

Supported starting with Windows 8.1.

|Value|Meaning|
|--- |--- |
|STATUS_SUCCESS|The chunk was successfully added to the queue.|
|STATUS_INVALID_PARAMETER|Parameters were validated and determined to be incorrect.|
|STATUS_NO_MEMORY|The interrupt-service-routine (ISR) ran out of free encode chunks.|


### -field DmaPageFaulted

Page faulted.

### -field DmaPageFaulted.FaultedFenceId

Submission fence ID of faulted command.


If the faulted fence cannot be determined reliably, <b>PageFaultFlags</b> should have <b>DXGK_PAGE_FAULT_FENCE_INVALID</b> bit set, and <b>FaultedFenceId</b> should be set to 0.


Supported starting with Windows 10.


### -field DmaPageFaulted.FaultedPrimitiveAPISequenceNumber

 When per draw fence write is enabled, this identifies the draw operation that caused the page fault, or <b>DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN</b> if such information is not available.

Supported starting with Windows 10.


### -field DmaPageFaulted.FaultedPipelineStage

Render pipeline stage during which the fault was generated, or <b>DXGK_RENDER_PIPELINE_STAGE_UNKNOWN</b> if such information is not available.

Supported starting with Windows 10.


### -field DmaPageFaulted.FaultedBindTableEntry

A bind table index of a resource being accessed at the time of the fault, or <b>DXGK_BIND_TABLE_ENTRY_UNKNOWN</b> if such information is not available.

Supported starting with Windows 10.


### -field DmaPageFaulted.PageFaultFlags

Flags described in <a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md">DXGK_PAGE_FAULT_FLAGS</a> enumeration specifying the nature of the fault.

Supported starting with Windows 10.


### -field DmaPageFaulted.FaultedVirtualAddress

GPU virtual address of fault, or <b>D3DGPU_NULL</b> if the fault has another cause. In the latter case, <b>FaultErrorCode</b> field should be used to describe the GPU error.

Supported starting with Windows 10.


### -field DmaPageFaulted.NodeOrdinal

Node ordinal of the engine generating the notification.

Supported starting with Windows 10.


### -field DmaPageFaulted.EngineOrdinal

Engine ordinal of the engine generating the notification.

Supported starting with Windows 10.


### -field DmaPageFaulted.PageTableLevel

Describes page table level that the faulting operation was attempted on.

Supported starting with Windows 10.


### -field DmaPageFaulted.FaultErrorCode


<a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_fault_error_code.md">DXGK_FAULT_ERROR_CODE</a> structure describing the error.

Supported starting with Windows 10.


### -field DmaPageFaulted.FaultedProcessHandle

DirectX graphics kernel process handle of the process that generated page fault, or <b>NULL</b> if the faulted process cannot be determined.

Supported starting with Windows 10.


### -field CrtcVsyncWithMultiPlaneOverlay2


Vsync with multi-plane overlay.

### -field CrtcVsyncWithMultiPlaneOverlay2.VidPnTargetId


Vsync with multiplane overlay Vidpn target id.

### -field CrtcVsyncWithMultiPlaneOverlay2.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member.


### -field CrtcVsyncWithMultiPlaneOverlay2.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display.

### -field CrtcVsyncWithMultiPlaneOverlay2.pMultiPlaneOverlayVsyncInfo

A pointer to a DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure that specifies information for each overlay plane updated by the VSync.


### -field CrtcVsyncWithMultiPlaneOverlay2.GpuFrequency

The frequency of the GPU clock counter.

### -field CrtcVsyncWithMultiPlaneOverlay2.GpuClockCounter

The GPU clock counter at the time of the VSYNC interrupt. Combined with GpuFrequency, this indicates the time of the VSYNC interrupt.

### -field MonitoredFenceSignaled

Monitored fence signaled.


### -field MonitoredFenceSignaled.NodeOrdinal

[in] Node ordinal of engine generating the notification.


### -field MonitoredFenceSignaled.EngineOrdinal


[in] Engine ordinal of engine generating the notification.

### -field HwContextListSwitchCompleted


Hardware context list switch is completed.

### -field HwContextListSwitchCompleted.NodeOrdinal

[in] Node ordinal of engine generating the notification.


### -field HwContextListSwitchCompleted.EngineOrdinal

[in] Engine ordinal of engine generating the notification.


### -field HwContextListSwitchCompleted.ContextSwitchFence

[in] Context switch fence used to perform this switch operation.


### -field HwQueuePageFaulted

Hardware queue page faulted.


### -field HwQueuePageFaulted.FaultedFenceId

[in] HW queue progress fence ID of the faulted command. If the faulted fence could not be determined reliably PageFaultFlags should have DXGK_PAGE_FAULT_FENCE_INVALID flag set.


### -field HwQueuePageFaulted.FaultedVirtualAddress

[in] Virtual address of fault, or 0 if the fault has another cause. In the latter case, FaultErrorCode field should be used to describe the GPU error.


### -field HwQueuePageFaulted.FaultedPrimitiveAPISequenceNumber

[in] When per draw fence write is enabled, identifies the draw that caused the page fault, or DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN if such information is not available.


### -field HwQueuePageFaulted.FaultedHwQueue




### -field HwQueuePageFaulted.FaultedHwContext




### -field HwQueuePageFaulted.FaultedProcessHandle




### -field HwQueuePageFaulted.NodeOrdinal


[in] Node ordinal of engine generating the notification.

### -field HwQueuePageFaulted.EngineOrdinal

[in] Engine ordinal of engine generating the notification.


### -field HwQueuePageFaulted.FaultedPipelineStage

[in] Render pipeline stage during which the fault was generated, or DXGK_RENDER_PIPELINE_STAGE_UNKNOWN if such information is not available.


### -field HwQueuePageFaulted.FaultedBindTableEntry

[in] A bind table index of a resource being accessed at the time of the fault, or DXGK_BIND_TABLE_ENTRY_UNKNOWN if such information is not available.


### -field HwQueuePageFaulted.PageFaultFlags

[in] Flags specifying the nature of the page fault and recovery policy.



### -field HwQueuePageFaulted.PageTableLevel


[in] Described page table level which the faulting operation was attempted on.


### -field HwQueuePageFaulted.FaultErrorCode

[in] Structure that contains error code describing the fault.

### -field HwQueuePageFaulted.FaultedHwQueue

[in] When DXGK_PAGE_FAULT_FENCE_INVALID is not set, specifies the handle of the HW queue that generated the fault.

### -field HwQueuePageFaulted.FaultedHwContext

[in] When DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_HW_CONTEXT_VALID are set, specifies the handle of the HW context that generated the fault.

### -field HwQueuePageFaulted.FaultedProcessHandle

[in] When DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_PROCESS_HANDLE_VALID are set, specifies the handle of the process that generated the fault.

### -field PeriodicMonitoredFenceSignaled


Periodic monitored fence signaled.

### -field PeriodicMonitoredFenceSignaled.VidPnTargetId

[in] The display signaling the monitored fence.


### -field PeriodicMonitoredFenceSignaled.NotificationID

[in] The notification id as multiple can be attached to one VidPnSource.

### -field SchedulingLogInterrupt

The scheduling log interrupt.

### -field SchedulingLogInterrupt.NodeOrdinal

[in] Node ordinal of engine that raised the scheduling log interrupt.

### -field SchedulingLogInterrupt.EngineOrdinal

[in] Engine ordinal of engine that raised the scheduling log interrupt.

### -field GpuEngineTimeout

GPU engine timeout.

### -field GpuEngineTimeout.NodeOrdinal

[in] Node ordinal of engine that timed out and needs the reset.

### -field GpuEngineTimeout.EngineOrdinal

[in] Engine ordinal of engine that timed out and needs the reset.

### -field SuspendContextCompleted

Suspend context completed.

### -field SuspendContextCompleted.hContext

[in] Hardware context that the suspend acknowledgment is for.

### -field SuspendContextCompleted.ContextSuspendFence

[in] Context suspend fence.

### -field Reserved


### -field Reserved.Reserved

An array of 32-bit values that are reserved for future use.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md">DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS</a> structure that indicates if the display miniport driver provides a physical adapter mask in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.



## -remarks



Depending on the value in the <b>InterruptType</b> member, the display miniport driver should set the appropriate union member in the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure. For example, for the end of a direct memory access (DMA) buffer fence, which corresponds to a value of DXGK_INTERRUPT_DMA_COMPLETED in <b>InterruptType</b>, the driver must set a value in the <b>SubmissionFenceId</b> member of the <b>DmaCompleted</b> member. This value should be the DMA buffer fence identifier, which the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function assigned to the just completed DMA buffer.




## -see-also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md">DXGK_MIRACAST_CAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md">DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md">DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md">DXGK_PAGE_FAULT_FLAGS</a>



<a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md">DXGK_MIRACAST_CHUNK_INFO</a>



 

 



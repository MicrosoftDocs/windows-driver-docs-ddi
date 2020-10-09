---
UID: NS:d3dkmddi._DXGKARGCB_NOTIFY_INTERRUPT_DATA
title: _DXGKARGCB_NOTIFY_INTERRUPT_DATA (d3dkmddi.h)
description: The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information for an interrupt.
old-location: display\dxgkargcb_notify_interrupt_data.htm
ms.assetid: c71078fb-5666-4038-81a0-de9375bafb5c
ms.date: 05/27/2020
keywords: ["DXGKARGCB_NOTIFY_INTERRUPT_DATA structure"]
ms.keywords: "*IN_CONST_PDXGKARGCB_NOTIFY_INTERRUPT_DATA, DXGKARGCB_NOTIFY_INTERRUPT_DATA, DXGKARGCB_NOTIFY_INTERRUPT_DATA structure [Display Devices], DmStructs_071ed85c-70d6-44d8-95e3-7f6609331f4f.xml, STATUS_INVALID_PARAMETER, STATUS_NO_MEMORY, STATUS_SUCCESS, _DXGKARGCB_NOTIFY_INTERRUPT_DATA, d3dkmddi/DXGKARGCB_NOTIFY_INTERRUPT_DATA, display.dxgkargcb_notify_interrupt_data"
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
 - DXGKARGCB_NOTIFY_INTERRUPT_DATA
---

# DXGKARGCB_NOTIFY_INTERRUPT_DATA structure


## -description

The **DXGKARGCB_NOTIFY_INTERRUPT_DATA** structure describes notification information for an interrupt.

## -struct-fields

### -field InterruptType

[in] A [**DXGK_INTERRUPT_TYPE**](..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md)-typed value that indicates the type of interrupt the display miniport driver is notifying the GPU scheduler about.

### -field DmaCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_COMPLETED**.

### -field DmaCompleted.SubmissionFenceId

[in] The DMA buffer fence identifier of the completed command. This identifier was assigned during a call to the driver's [**DXGKDDI_SUBMITCOMMAND**](./nc-d3dkmddi-dxgkddi_submitcommand.md) function for the latest completed DMA buffer.

### -field DmaCompleted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.

### -field DmaCompleted.EngineOrdinal

[in] The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to.

### -field DmaPreempted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_PREEMPTED**.

### -field DmaPreempted.PreemptionFenceId

[in] The submission identifier of the preempting request.

### -field DmaPreempted.LastCompletedFenceId

[in] The submission identifier of the last completed command before preemption.

### -field DmaPreempted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.

### -field DmaPreempted.EngineOrdinal

[in] The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** set to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to. The GPU scheduler determines that hardware preempted all commands between the preemption request and the submission that **LastCompletedFenceId** specifies.

### -field DmaFaulted

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_FAULTED**.

### -field DmaFaulted.FaultedFenceId

[in] The identifier of the faulty command.

### -field DmaFaulted.Status

[in] The status of the faulty command.

### -field DmaFaulted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.

### -field DmaFaulted.EngineOrdinal

[in] The zero-based index of the engine, within the node that **NodeOrdinal** specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set **EngineOrdinal** to 0. For graphics adapters that are part of a link, set **EngineOrdinal** to the adapter index of the adapter in the link that the interrupting engine belongs to.

### -field CrtcVsync

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC**.

### -field CrtcVsync.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.

### -field CrtcVsync.PhysicalAddress

[in] The physical address of the displaying buffer. When monitor visibility is off, the operating system still expects a non-**NULL** physical address. This address should be set to the physical address that the pixel pipeline would read from if visibility were on.

### -field CrtcVsync.PhysicalAdapterMask

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member.

### -field DisplayOnlyVsync

Structure used when **InterruptType** is **DXGK_INTERRUPT_DISPLAYONLY_VSYNC**. Supported starting with Windows 8.

### -field DisplayOnlyVsync.VidPnTargetId

[in] For a display-only driver, the zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY**. Provides VSync notifications for display miniport drivers that support multiplane overlays. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.PhysicalAdapterMask

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the **ValidPhysicalAdapterMask** bit-field flag in the **Flags** member. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display. Supported starting with Windows 8.

### -field CrtcVsyncWithMultiPlaneOverlay.pMultiPlaneOverlayVsyncInfo

[in] A pointer to  a [**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO**](..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md) structure that specifies an overlay plane to display during a VSync interval. Supported starting with Windows 8.1.

### -field DisplayOnlyPresentProgress

[in] A [**DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS**](./ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md) structure that provides the progress of a kernel mode display-only driver's (KMDOD) present operation. Used when **InterruptType** is **DXGK_INTERRUPT_DISPLAYONLY_PRESENT_PROGRESS**. Supported starting with Windows 8.

### -field MiracastEncodeChunkCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_MICACAST_CHUNK_PROCESSING_COMPLETE**. Supported by WDDM 1.3 and later display miniport drivers running on Windows 8.1 and later.

### -field MiracastEncodeChunkCompleted.VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the encoding is being performed. Supported starting with Windows 8.1.

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

Structure used when **InterruptType** is **DXGK_INTERRUPT_DMA_PAGE_FAULTED**.

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

[**DXGK_FAULT_ERROR_CODE**](..\d3dkmdt\ns-d3dkmdt-_dxgk_fault_error_code.md) structure describing the error. Supported starting with Windows 10.

### -field DmaPageFaulted.FaultedProcessHandle

DirectX graphics kernel process handle of the process that generated page fault, or **NULL** if the faulted process cannot be determined. Supported starting with Windows 10.

### -field CrtcVsyncWithMultiPlaneOverlay2

Structure used when **InterruptType** is **DXGK_INTERRUPT_CRTC_VSYNC_WITH_MULTIPLANE_OVERLAY2**. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.VidPnTargetId

Vsync with multiplane overlay Vidpn target id. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.pMultiPlaneOverlayVsyncInfo

A pointer to a DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure that specifies information for each overlay plane updated by the VSync. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.GpuFrequency

The frequency of the GPU clock counter. Supported starting with Windows 10, version 1607.

### -field CrtcVsyncWithMultiPlaneOverlay2.GpuClockCounter

The GPU clock counter at the time of the VSYNC interrupt. Combined with GpuFrequency, this indicates the time of the VSYNC interrupt. Supported starting with Windows 10, version 1607.

### -field MonitoredFenceSignaled

Structure used when **InterruptType** is **DXGK_INTERRUPT_MONITORED_FENCE_SIGNALED**. Supported starting with Windows 10, version 1703.

### -field MonitoredFenceSignaled.NodeOrdinal

[in] Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field MonitoredFenceSignaled.EngineOrdinal

[in] Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_HWCONTEXTLIST_SWITCH_COMPLETED**. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.NodeOrdinal

[in] Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.EngineOrdinal

[in] Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwContextListSwitchCompleted.ContextSwitchFence

[in] Context switch fence used to perform this switch operation. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted

Structure used when **InterruptType** is **DXGK_INTERRUPT_HWQUEUE_PAGE_FAULTED**. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedFenceId

[in] HW queue progress fence ID of the faulted command. If the faulted fence could not be determined reliably PageFaultFlags should have DXGK_PAGE_FAULT_FENCE_INVALID flag set. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedVirtualAddress

[in] Virtual address of fault, or 0 if the fault has another cause. In the latter case, FaultErrorCode field should be used to describe the GPU error. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedPrimitiveAPISequenceNumber

[in] When per draw fence write is enabled, identifies the draw that caused the page fault, or DXGK_PRIMITIVE_API_SEQUENCE_NUMBER_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedHwQueue

[in] When DXGK_PAGE_FAULT_FENCE_INVALID is not set, specifies the handle of the HW queue that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedHwContext

[in] When DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_HW_CONTEXT_VALID are set, specifies the handle of the HW context that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedProcessHandle

[in] Wen DXGK_PAGE_FAULT_FENCE_INVALID and DXGK_PAGE_FAULT_PROCESS_HANDLE_VALID are set, specifies the handle of the process that generated the fault. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.NodeOrdinal

[in] Node ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.EngineOrdinal

[in] Engine ordinal of engine generating the notification. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedPipelineStage

[in] Render pipeline stage during which the fault was generated, or DXGK_RENDER_PIPELINE_STAGE_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultedBindTableEntry

[in] A bind table index of a resource being accessed at the time of the fault, or DXGK_BIND_TABLE_ENTRY_UNKNOWN if such information is not available. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.PageFaultFlags

[in] Flags specifying the nature of the page fault and recovery policy. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.PageTableLevel

[in] Described page table level which the faulting operation was attempted on. Supported starting with Windows 10, version 1703.

### -field HwQueuePageFaulted.FaultErrorCode

[in] Structure that contains error code describing the fault. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled

Structure used when **InterruptType** is **DXGK_INTERRUPT_PERIODIC_MONITORED_FENCE_SIGNALED**. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled.VidPnTargetId

[in] The display signaling the monitored fence. Supported starting with Windows 10, version 1703.

### -field PeriodicMonitoredFenceSignaled.NotificationID

[in] The notification id as multiple can be attached to one VidPnSource. Supported starting with Windows 10, version 1703.

### -field SchedulingLogInterrupt

Structure used when **InterruptType** is **DXGK_INTERRUPT_SCHEDULING_LOG_INTERRUPT**. Supported starting with Windows 10, version 1803.

### -field SchedulingLogInterrupt.NodeOrdinal

[in] Node ordinal of engine that raised the scheduling log interrupt. Supported starting with Windows 10, version 1803.

### -field SchedulingLogInterrupt.EngineOrdinal

[in] Engine ordinal of engine that raised the scheduling log interrupt. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout

Structure used when **InterruptType** is **DXGK_INTERRUPT_GPU_ENGINE_TIMEOUT**. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout.NodeOrdinal

[in] Node ordinal of engine that timed out and needs the reset. Supported starting with Windows 10, version 1803.

### -field GpuEngineTimeout.EngineOrdinal

[in] Engine ordinal of engine that timed out and needs the reset. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted

Structure used when **InterruptType** is **DXGK_INTERRUPT_SUSPEND_CONTEXT_COMPLETED**. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted.hContext

[in] Hardware context that the suspend acknowledgment is for. Supported starting with Windows 10, version 1803.

### -field SuspendContextCompleted.ContextSuspendFence

[in] Context suspend fence. Supported starting with Windows 10, version 1803.

### -field Reserved

Reserved for future use.

### -field Reserved.Reserved

An array of 32-bit values that are reserved for future use.

### -field Flags

[in] A [**DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS**](..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md) structure that indicates if the display miniport driver provides a physical adapter mask in a call to the [**DxgkCbNotifyInterrupt**](..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md) function.

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

#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
      DXGK_MIRACAST_CHUNK_INFO       ChunkInfo;
      PVOID                          pPrivateDriverData;
      UINT                           PrivateDataDriverSize;
      NTSTATUS                       Status;
    } MiracastEncodeChunkCompleted;
#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3)

#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
    struct {
      UINT                        FaultedFenceId;
      UINT64                      FaultedPrimitiveAPISequenceNumber;
      DXGK_RENDER_PIPELINE_STAGE  FaultedPipelineStage;
      UINT                        FaultedBindTableEntry;
      DXGK_PAGE_FAULT_FLAGS       PageFaultFlags;
      D3DGPU_VIRTUAL_ADDRESS      FaultedVirtualAddress;
      UINT                        NodeOrdinal;
      UINT                        EngineOrdinal;
      UINT                        PageTableLevel;
      DXGK_FAULT_ERROR_CODE       FaultErrorCode;
      HANDLE                      FaultedProcessHandle;
    } DmaPageFaulted;
#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)

#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_1)
    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID                VidPnTargetId;
      UINT                                          PhysicalAdapterMask;
      UINT                                          MultiPlaneOverlayVsyncInfoCount;
      _Field_size_(MultiPlaneOverlayVsyncInfoCount) DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 *pMultiPlaneOverlayVsyncInfo;
      ULONGLONG                                     GpuFrequency;
      ULONGLONG                                     GpuClockCounter;
    } CrtcVsyncWithMultiPlaneOverlay2;

#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_1)

#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
    struct {
      UINT    NodeOrdinal;
      UINT    EngineOrdinal;
    } MonitoredFenceSignaled;

    struct {
      UINT    NodeOrdinal;
      UINT    EngineOrdinal;
      UINT64  ContextSwitchFence;
    } HwContextListSwitchCompleted;

    struct {
      UINT64                      FaultedFenceId;
      D3DGPU_VIRTUAL_ADDRESS      FaultedVirtualAddress;
      UINT64                      FaultedPrimitiveAPISequenceNumber;

      union {
        HANDLE                  FaultedHwQueue;
        HANDLE                  FaultedHwContext;
        HANDLE                  FaultedProcessHandle;
      };

      UINT                        NodeOrdinal;
      UINT                        EngineOrdinal;

      DXGK_RENDER_PIPELINE_STAGE  FaultedPipelineStage;
      UINT                        FaultedBindTableEntry;
      DXGK_PAGE_FAULT_FLAGS       PageFaultFlags;
      UINT                        PageTableLevel;
      DXGK_FAULT_ERROR_CODE       FaultErrorCode;
    } HwQueuePageFaulted;

    struct {
      D3DDDI_VIDEO_PRESENT_TARGET_ID    VidPnTargetId;
      UINT                              NotificationID;
    } PeriodicMonitoredFenceSignaled;

#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)

#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_4)
    struct {
      UINT    NodeOrdinal;
      UINT    EngineOrdinal;
    } SchedulingLogInterrupt;

    struct {
      UINT    NodeOrdinal;
      UINT    EngineOrdinal;
    } GpuEngineTimeout;

    struct {
      HANDLE  hContext;
      UINT64  ContextSuspendFence;
    } SuspendContextCompleted;

#endif // (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_4)

    struct {
      UINT Reserved[16];
    } Reserved;
  };
  DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS Flags;
} DXGKARGCB_NOTIFY_INTERRUPT_DATA;
```

## -remarks

A miniport driver fills in **DXGKARGCB_NOTIFY_INTERRUPT_DATA**, and then uses the [**DXGKCB_SYNCHRONIZE_EXECUTION**](../dispmprt/nc-dispmprt-dxgkcb_synchronize_execution.md) callback to sync with the interrupt. The **SynchronizeRoutine** parameter of the **DXGKCB_SYNCHRONIZE_EXECUTION** callback points to a miniport-implemented function that gets called by the OS when appropriate, and then the driver fills out the parameter info before calling back into the OS with the [**DXGKCB_NOTIFY_INTERRUPT**](./nc-d3dkmddi-dxgkcb_notify_interrupt.md) callback. The OS then handles the interrupt, with the scheduler using information in the DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 struct.

Depending on the value in the **InterruptType** member, the display miniport driver should set the appropriate union member in this structure. For example, for the end of a direct memory access (DMA) buffer fence, which corresponds to a value of DXGK_INTERRUPT_DMA_COMPLETED in **InterruptType**, the driver must set a value in the **SubmissionFenceId** member of the **DmaCompleted** member. This value should be the DMA buffer fence identifier, which the driver's [**DxgkDdiSubmitCommand**](..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md) function assigned to the just completed DMA buffer.

## -see-also

[**DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS**](..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md)

[**DXGK_INTERRUPT_TYPE**](..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md)

[**DxgkDdiSubmitCommand**](..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md)

[**DxgkCbNotifyInterrupt**](..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[**DXGK_MIRACAST_CAPS**](..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md)

[**DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO**](..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md)

[**DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS**](..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md)

[**DXGK_PAGE_FAULT_FLAGS**](..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md)

[**DXGK_MIRACAST_CHUNK_INFO**](..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md)
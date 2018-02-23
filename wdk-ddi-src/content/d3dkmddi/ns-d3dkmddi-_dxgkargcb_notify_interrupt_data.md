---
UID: NS:d3dkmddi._DXGKARGCB_NOTIFY_INTERRUPT_DATA
title: "_DXGKARGCB_NOTIFY_INTERRUPT_DATA"
author: windows-driver-content
description: The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information.
old-location: display\dxgkargcb_notify_interrupt_data.htm
old-project: display
ms.assetid: c71078fb-5666-4038-81a0-de9375bafb5c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: STATUS_NO_MEMORY, DmStructs_071ed85c-70d6-44d8-95e3-7f6609331f4f.xml, *IN_CONST_PDXGKARGCB_NOTIFY_INTERRUPT_DATA, display.dxgkargcb_notify_interrupt_data, STATUS_INVALID_PARAMETER, DXGKARGCB_NOTIFY_INTERRUPT_DATA, d3dkmddi/DXGKARGCB_NOTIFY_INTERRUPT_DATA, _DXGKARGCB_NOTIFY_INTERRUPT_DATA, DXGKARGCB_NOTIFY_INTERRUPT_DATA structure [Display Devices], STATUS_SUCCESS
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARGCB_NOTIFY_INTERRUPT_DATA
product: Windows
targetos: Windows
req.typenames: DXGKARGCB_NOTIFY_INTERRUPT_DATA
---

# _DXGKARGCB_NOTIFY_INTERRUPT_DATA structure


## -description


The DXGKARGCB_NOTIFY_INTERRUPT_DATA structure describes notification information.


## -syntax


````
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
      DXGK_MIRACAST_CHUNK_INFO       ChunkInfo;
      PVOID                          pPrivateDriverData;
      UINT                           PrivateDataDriverSize;
      NTSTATUS                       Status;
    } MiracastEncodeChunkCompleted;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_0)
    struct {
      UINT                       FaultedFenceId;
      UINT64                     FaultedPrimitiveAPISequenceNumber;
      DXGK_RENDER_PIPELINE_STAGE FaultedPipelineStage;
      UINT                       FaultedBindTableEntry;
      DXGK_PAGE_FAULT_FLAGS      PageFaultFlags;
      D3DGPU_VIRTUAL_ADDRESS     FaultedVirtualAddress;
      UINT                       NodeOrdinal;
      UINT                       EngineOrdinal;
      UINT                       PageTableLevel;
      DXGK_FAULT_ERROR_CODE      FaultErrorCode;
      HANDLE                     FaultedProcessHandle;
    } DmaPageFaulted;
#endif 
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM2_2)
    D3DDDI_VIDEO_PRESENT_TARGET_ID         VidPnTargetId;
    UINT                                   PhysicalAdapterMask;
    UINT                                   MultiPlaneOverlayVsyncInfoCount;
    DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2    *pMultiPlaneOverlayVsyncInfo;
    ULONGLONG                              GpuFrequency;
    ULONGLONG                              GpuClockCounter;
#endif 
    struct {
      UINT Reserved[16];
    } Reserved;
  };
  DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS Flags;
} DXGKARGCB_NOTIFY_INTERRUPT_DATA;
````


## -struct-fields




### -field InterruptType

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>-typed value that indicates the type of interrupt that the display miniport driver notifies the GPU scheduler about.


### -field DmaCompleted


### -field DmaCompleted.SubmissionFenceId

[in] The submission identifier of the completed command.


### -field DmaCompleted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.


### -field DmaCompleted.EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set <b>EngineOrdinal</b> to 0. For graphics adapters that are part of a link, set <b>EngineOrdinal</b> to the adapter index of the adapter in the link that the interrupting engine belongs to.


### -field DmaPreempted


### -field DmaPreempted.PreemptionFenceId

[in] The submission identifier of the preempting request.


### -field DmaPreempted.LastCompletedFenceId

[in] The submission identifier of the last completed command before preemption.


### -field DmaPreempted.NodeOrdinal

[in] The zero-based index of the node that generates the notification.


### -field DmaPreempted.EngineOrdinal

[in] The zero-based index of the engine, within the node that <b>NodeOrdinal</b> specifies, that generates the notification. For graphics adapters that are not part of a link, you should always set <b>EngineOrdinal</b> set to 0. For graphics adapters that are part of a link, set <b>EngineOrdinal</b> to the adapter index of the adapter in the link that the interrupting engine belongs to. The GPU scheduler determines that hardware preempted all commands between the preemption request and the submission that <b>LastCompletedFenceId</b> specifies.


### -field DmaFaulted


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

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="STATUS_SUCCESS"></a><a id="status_success"></a><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The chunk was successfully added to the queue.

</td>
</tr>
<tr>
<td width="40%"><a id="STATUS_INVALID_PARAMETER"></a><a id="status_invalid_parameter"></a><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.


</td>
</tr>
<tr>
<td width="40%"><a id="STATUS_NO_MEMORY"></a><a id="status_no_memory"></a><dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>
</td>
<td width="60%">
The interrupt-service-routine (ISR) ran out of free encode chunks.

</td>
</tr>
</table>
 


### -field DmaPageFaulted


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

 


### -field CrtcVsyncWithMultiPlaneOverlay2.VidPnTargetId

 


### -field CrtcVsyncWithMultiPlaneOverlay2.PhysicalAdapterMask

 


### -field CrtcVsyncWithMultiPlaneOverlay2.MultiPlaneOverlayVsyncInfoCount

 


### -field CrtcVsyncWithMultiPlaneOverlay2.pMultiPlaneOverlayVsyncInfo

 


### -field CrtcVsyncWithMultiPlaneOverlay2.GpuFrequency

 


### -field CrtcVsyncWithMultiPlaneOverlay2.GpuClockCounter

 


### -field MonitoredFenceSignaled

 


### -field MonitoredFenceSignaled.NodeOrdinal

 


### -field MonitoredFenceSignaled.EngineOrdinal

 


### -field HwContextListSwitchCompleted

 


### -field HwContextListSwitchCompleted.NodeOrdinal

 


### -field HwContextListSwitchCompleted.EngineOrdinal

 


### -field HwContextListSwitchCompleted.ContextSwitchFence

 


### -field HwQueuePageFaulted

 


### -field HwQueuePageFaulted.FaultedFenceId

 


### -field HwQueuePageFaulted.FaultedVirtualAddress

 


### -field HwQueuePageFaulted.FaultedPrimitiveAPISequenceNumber

 


### -field HwQueuePageFaulted.NodeOrdinal

 


### -field HwQueuePageFaulted.EngineOrdinal

 


### -field HwQueuePageFaulted.FaultedPipelineStage

 


### -field HwQueuePageFaulted.FaultedBindTableEntry

 


### -field HwQueuePageFaulted.PageFaultFlags

 


### -field HwQueuePageFaulted.PageTableLevel

 


### -field HwQueuePageFaulted.FaultErrorCode

 


### -field PeriodicMonitoredFenceSignaled

 


### -field PeriodicMonitoredFenceSignaled.VidPnTargetId

 


### -field PeriodicMonitoredFenceSignaled.NotificationID

 


### -field Reserved


### -field Reserved.Reserved

An array of 32-bit values that are reserved for future use.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md">DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS</a> structure that indicates if the display miniport driver provides a physical adapter mask in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function.


#### - DisplayOnlyPresentProgress

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a> structure that provides the progress of a kernel mode display-only driver's (KMDOD) present operation.

Supported starting with Windows 8.


#### - VidPnTargetId

The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.


#### - PhysicalAdapterMask

The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member.


#### - MultiPlaneOverlayVsyncInfoCount

The number of overlay planes that are available to display.


#### - pMultiPlaneOverlayVsyncInfo

A pointer to a DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure that specifies information for each overlay plane updated by the VSync.


#### - GpuFrequency

The frequency of the GPU clock counter. 


#### - GpuClockCounter

The GPU clock counter at the time of the VSYNC interrupt. Combined with GpuFrequency, this indicates the time of the VSYNC interrupt. 


## -remarks



Depending on the value in the <b>InterruptType</b> member, the display miniport driver should set the appropriate union member in the DXGKARGCB_NOTIFY_INTERRUPT_DATA structure. For example, for the end of a direct memory access (DMA) buffer fence, which corresponds to a value of DXGK_INTERRUPT_DMA_COMPLETED in <b>InterruptType</b>, the driver must set a value in the <b>SubmissionFenceId</b> member of the <b>DmaCompleted</b> member. This value should be the DMA buffer fence identifier, which the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function assigned to the just completed DMA buffer.




## -see-also

<a href="..\dispmprt\ns-dispmprt-_dxgk_miracast_caps.md">DXGK_MIRACAST_CAPS</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_dxgk_page_fault_flags.md">DXGK_PAGE_FAULT_FLAGS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkcb_notify_interrupt_data_flags.md">DXGKCB_NOTIFY_INTERRUPT_DATA_FLAGS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkargcb_present_displayonly_progress.md">DXGKARGCB_PRESENT_DISPLAYONLY_PROGRESS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_vsync_info.md">DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO</a>



<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_interrupt_type.md">DXGK_INTERRUPT_TYPE</a>



<a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_info.md">DXGK_MIRACAST_CHUNK_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_NOTIFY_INTERRUPT_DATA structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:d3dkmddi._DXGK_DRIVERCAPS
title: _DXGK_DRIVERCAPS (d3dkmddi.h)
description: The DXGK_DRIVERCAPS structure describes capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_drivercaps.htm
ms.assetid: 1ee8eb02-066c-4a54-b31a-cd6644cbce06
ms.date: 03/24/2020
keywords: ["DXGK_DRIVERCAPS structure"]
ms.keywords: DXGK_DRIVERCAPS, DXGK_DRIVERCAPS structure [Display Devices], DmStructs_4a8b7d02-5b36-4a4b-980f-edfc96b4efd3.xml, _DXGK_DRIVERCAPS, d3dkmddi/DXGK_DRIVERCAPS, display.dxgk_drivercaps
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.typenames: DXGK_DRIVERCAPS
ms.custom: 19H1
f1_keywords:
 - _DXGK_DRIVERCAPS
 - d3dkmddi/_DXGK_DRIVERCAPS
 - DXGK_DRIVERCAPS
 - d3dkmddi/DXGK_DRIVERCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_DRIVERCAPS
dev_langs:
 - c++
---

# _DXGK_DRIVERCAPS structure


## -description

The DXGK_DRIVERCAPS structure describes capabilities of a display miniport driver that the driver provides through a call to its [*DxgkDdiQueryAdapterInfo*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

## -struct-fields

### -field HighestAcceptableAddress

[out] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the highest acceptable physical address of system memory (RAM) to use.

### -field MaxAllocationListSlotId

[out] The maximum number of allocation-list slot identifiers. An allocation-list slot represents where an allocation is directed in direct memory access (DMA) buffering.

### -field ApertureSegmentCommitLimit

[out] The maximum number of bytes of physical memory that the display miniport driver supports for mapping into an aperture segment. The video memory manager will not map more physical memory into an aperture segment than the limit that **ApertureSegmentCommitLimit** specifies.

### -field MaxPointerWidth

[out] The maximum width of the mouse pointer, in pixels.

### -field MaxPointerHeight

[out] The maximum height of the mouse pointer, in scan lines.

### -field PointerCaps

[out] A [**DXGK_POINTERFLAGS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md) structure that identifies the mouse pointer capabilities, in bit-field flags, that the driver can support.

### -field InterruptMessageNumber

[out] The message number that is used if message-signaled interrupts are used and the driver calls the [*DxgkCbNotifyInterrupt*](..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md) function from the interrupt handler corresponding to a fixed message number.

### -field NumberOfSwizzlingRanges

[out] The number of swizzling ranges that the driver can support.

### -field MaxOverlays

[out] The maximum number of overlays that the driver can support.

### -field GammaRampCaps

[out] A [**DXGK_GAMMARAMPCAPS**](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_gammarampcaps) structure that identifies the gamma-ramp capabilities, in bit-field flags, that the driver can support.

### -field ColorTransformCaps

[out] Flags to describe gamma and color space transform capabilities of the display pipelines. NOTE: This field replaces the GammaRampCaps in the pre-WDDM 2.2 version of this structure.

### -field PresentationCaps

[out] A [**DXGK_PRESENTATIONCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md) structure that identifies the presentation capabilities, in bit-field flags, that the driver can support.

### -field MaxQueuedFlipOnVSync

[out] The number of flips that can be queued and pending at the graphics hardware. Each flip is latched to a digital-to-analog converter (DAC) at every VSync interrupt, in order, as the graphics hardware queues the flip.

### -field FlipCaps

[out] A [**DXGK_FLIPCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_flipcaps.md) structure that identifies the flipping capabilities, in bit-field flags, that the driver can support.

### -field SchedulingCaps

[out] A [**DXGK_VIDSCHCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md) structure that identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that the driver can support.

### -field MemoryManagementCaps

[out] A [**DXGK_VIDMMCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md) structure that identifies the video memory management capabilities that the driver can support.

### -field GpuEngineTopology

[out] A [**DXGK_GPUENGINETOPOLOGY**](..\d3dkmddi\ns-d3dkmddi-_dxgk_gpuenginetopology.md) structure that describes the GPU-engine topology that the driver can support.

### -field WDDMVersion

[out] If a driver supports Windows 7 or later features (DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7), this member is reserved and should be set to zero.

NOTE: If a driver does not support Windows 7 or later features (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), set this member to DXGKDDI_WDDMv1.

NOTE: If a driver does not support Windows 7 or later features (DXGKDDI_INTERFACE_VERSION < DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 8 WDK, set this member to DXGKDDI_WDDMv1_2.

Supported starting with Windows 7.

### -field Reserved

Reserved.

### -field Reserved1

Reserved.

### -field PreemptionCaps

[out] A [**D3DKMDT_PREEMPTION_CAPS**](..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_preemption_caps.md) structure that describes the capabilities for the preemption of GPU graphics requests that the driver supports.

Supported starting with Windows 8.

### -field SupportNonVGA

[out] If **TRUE**, the driver supports resetting the  display device and releasing ownership of the current  power-on self-test (POST)  device by using the [*DxgkDdiStopDeviceAndReleasePostDisplayOwnership*](..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md) function.

Supported starting with Windows 8.

### -field SupportSmoothRotation

[out] If **TRUE**, the driver supports updating path rotation on the adapter by using the [*DxgkDdiUpdateActiveVidPnPresentPath*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md) function, while not requiring a new VidPN to be created and set.

Supported starting with Windows 8.

### -field SupportPerEngineTDR

[out] If **TRUE**, the driver supports resetting individual GPU engines.

If this member is set, the display miniport driver must implement the [*DxgkDdiQueryDependentEngineGroup*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md), [*DxgkDdiQueryEngineStatus*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md), and [*DxgkDdiResetEngine*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md) functions.

Supported starting with Windows 8.

### -field SupportDirectFlip

[out] If **TRUE**, the driver supports the creation and opening of shared managed primary allocations. A value of **TRUE** also indicates the following:

- The display miniport driver guarantees that when the [*DxgkDdiSetVidPnSourceAddress*](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)) function is called, the driver does not allow video memory to be flipped to an incompatible allocation.
- The user mode driver validates Direct Flip resources before the Desktop Windows Manager (DWM) uses them.

Only the DWM can flip video memory to Direct Flip resources. The DWM validates these resources using the user-mode [*CheckDirectFlipSupport*](..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md) function.

Supported starting with Windows 8.

### -field SupportMultiPlaneOverlay

[out] If **TRUE**, the display miniport driver supports multiplane overlays, and the driver should also set a value for the **MaxOverlayPlanes** member. If **FALSE**, the DirectX graphics kernel subsystem will not call multiplane overlay functions.

Supported starting with Windows 8.1.

### -field SupportRuntimePowerManagement

[out] If **TRUE**, the display miniport driver supports run-time power management.

If this member is set, the display miniport driver must implement the [*DxgkDdiSetPowerComponentFState*](..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md) and [*DxgkDdiPowerRuntimeControlRequest*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddipowerruntimecontrolrequest) functions.

Supported starting with Windows 8.

### -field SupportSurpriseRemovalInHibernation

[out] If **TRUE**, the display miniport driver supports cleaning up software resources after an external display device in hibernation mode is disconnected from the system.

If this member is set, the display miniport driver must implement the [*DxgkDdiNotifySurpriseRemoval*](..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md) function with the *RemovalType* parameter set to **DxgkRemovalHibernation**.

For more information, see [Using cross-adapter resources in a hybrid system](https://docs.microsoft.com/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

Supported starting with Windows 8.

### -field HybridDiscrete

[out] If **TRUE**, the display miniport driver is a discrete GPU in a [hybrid system](https://docs.microsoft.com/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

If this member is set, the display miniport driver should:

- support WDDM 1.3
- support cross-adapter resources
- have no display outputs

For more information, see [Using cross-adapter resources in a hybrid system](https://docs.microsoft.com/windows-hardware/drivers/display/using-cross-adapter-resources-in-a-hybrid-system).

Supported starting with Windows 8.1.

### -field MaxOverlayPlanes

[out] If **SupportRuntimePowerManagement** is **TRUE**, the display miniport driver should set **MaxOverlayPlanes** to the maximum number of overlay planes that can be simultaneously displayed on a single output, including the primary surface, that it can support. If the number of available planes will change when the operating mode changes, the driver should use a number that reflects the best-case scenario.

Supported starting with Windows 8.1.

### -field HybridIntegrated

Indicates whether the current GPU is hybrid.

### -field InternalGpuVirtualAddressRangeStart

Internal GPU virtual address range start.

### -field InternalGpuVirtualAddressRangeEnd

Internal GPU virtual address range end.

### -field SupportSurpriseRemoval

Support surprise removal.

### -field SupportMultiPlaneOverlayImmediateFlip

[out] If TRUE, the display miniport driver supports immediate flips to a multiplane overlay plane as long as the only value changing is the physical address to be displayed.

### -field CursorScaledWithMultiPlaneOverlayPlane0

[out] If TRUE, the display hardware will always apply the same scaling factor to the hardware cursor as is applied to plane 0 when per plane multiplane overlay stretching is applied.

### -field HybridAcpiChainingRequired

Indicates that this hybrid discrete driver requires chaining of ACPI events triggered on the integrated adapter.

### -field MaxQueuedMultiPlaneOverlayFlipVSync

[out] Indicates the maximum number of updates to a single plane can be made within a single VSYNC period, where the most recent update overrides the previous update.

### -field MiscCaps

Miscellaneous capabilities.

### -field MiscCaps.SupportContextlessPresent

Supports null context in DDI calls. When this value is set, the OS will pass NULL context in present related DDIs. Supported starting in WDDM 2.4.

### -field MiscCaps.Detachable

Detachable, i.e. hot-pluggable. Drivers will set this bit during adapter initialization if the adapter is hot-pluggable. Supported starting in WDDM 2.4.

### -field MiscCaps.VirtualGpuOnly

The adapter should not be used by Direct3D applications on the host. Supported starting in WDDM 2.5.

### -field MiscCaps.ComputeOnly

Supports Compute-Only devices by rendering WDDM's render-only device capabilities. Supported starting in Windows 10, version 1901 (WDDM 2.6)

### -field MiscCaps.IndependentVidPnVSyncControl

Drivers that set this capability should read the specified VidPnSourceId in DdiControlInterrupt3 and control VSync on the mentioned VidPnSourceId. Supported starting in Windows 10, version 2004 (WDDM 2.7).

### -field MiscCaps.Reserved

Reserved.

### -field MiscCaps.Value

## -see-also

[*DxgkDdiUpdateActiveVidPnPresentPath*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md)

[**DXGK_VIDSCHCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md)

[*DxgkDdiStopDeviceAndReleasePostDisplayOwnership*](..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md)

[*CheckDirectFlipSupport*](..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md)

[**DXGK_POINTERFLAGS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md)

[**D3DKMDT_PREEMPTION_CAPS**](..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_preemption_caps.md)

[**DXGK_GAMMARAMPCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_gammarampcaps.md)

[*DxgkDdiQueryAdapterInfo*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md)

[**DXGK_PRESENTATIONCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md)

[**DXGK_VIDMMCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md)

[**DXGK_GPUENGINETOPOLOGY**](..\d3dkmddi\ns-d3dkmddi-_dxgk_gpuenginetopology.md)

[*DxgkDdiQueryEngineStatus*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md)

[*DxgkDdiSetPowerComponentFState*](..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md)

[*DxgkDdiSetVidPnSourceAddress*](https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff560767(v=vs.85))

[*DxgkDdiResetEngine*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md)

[*DxgkDdiPowerRuntimeControlRequest*](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddipowerruntimecontrolrequest)

[*DxgkCbNotifyInterrupt*](..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md)

[*DxgkDdiNotifySurpriseRemoval*](..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md)

[*DxgkDdiQueryDependentEngineGroup*](..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md)

[**DXGK_FLIPCAPS**](..\d3dkmddi\ns-d3dkmddi-_dxgk_flipcaps.md)

[**DXGKARG_QUERYADAPTERINFO**](..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md)


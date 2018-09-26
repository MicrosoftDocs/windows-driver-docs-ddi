---
UID: NS:d3dkmddi._DXGK_DRIVERCAPS
title: "_DXGK_DRIVERCAPS"
author: windows-driver-content
description: The DXGK_DRIVERCAPS structure describes capabilities of a display miniport driver that the driver provides through a call to its DxgkDdiQueryAdapterInfo function.
old-location: display\dxgk_drivercaps.htm
ms.assetid: 1ee8eb02-066c-4a54-b31a-cd6644cbce06
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGK_DRIVERCAPS, DXGK_DRIVERCAPS structure [Display Devices], DmStructs_4a8b7d02-5b36-4a4b-980f-edfc96b4efd3.xml, _DXGK_DRIVERCAPS, d3dkmddi/DXGK_DRIVERCAPS, display.dxgk_drivercaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_DRIVERCAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_DRIVERCAPS
---

# _DXGK_DRIVERCAPS structure


## -description


The DXGK_DRIVERCAPS structure describes capabilities of a display miniport driver that the driver provides through a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.



## -struct-fields




### -field HighestAcceptableAddress

[out] A PHYSICAL_ADDRESS data type (which is defined as LARGE_INTEGER) that indicates the highest acceptable physical address of system memory (RAM) to use.


### -field MaxAllocationListSlotId

[out] The maximum number of allocation-list slot identifiers. An allocation-list slot represents where an allocation is directed in direct memory access (DMA) buffering.


### -field ApertureSegmentCommitLimit

[out] The maximum number of bytes of physical memory that the display miniport driver supports for mapping into an aperture segment. The video memory manager will not map more physical memory into an aperture segment than the limit that <b>ApertureSegmentCommitLimit</b> specifies.


### -field MaxPointerWidth

[out] The maximum width of the mouse pointer, in pixels.


### -field MaxPointerHeight

[out] The maximum height of the mouse pointer, in scan lines.


### -field PointerCaps

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md">DXGK_POINTERFLAGS</a> structure that identifies the mouse pointer capabilities, in bit-field flags, that the driver can support.


### -field InterruptMessageNumber

[out] The message number that is used if message-signaled interrupts are used and the driver calls the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a> function from the interrupt handler corresponding to a fixed message number.


### -field NumberOfSwizzlingRanges

[out] The number of swizzling ranges that the driver can support.


### -field MaxOverlays

[out] The maximum number of overlays that the driver can support.


### -field GammaRampCaps

[out] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561071">DXGK_GAMMARAMPCAPS</a> structure that identifies the gamma-ramp capabilities, in bit-field flags, that the driver can support.


### -field ColorTransformCaps

[out] Flags to describe gamma and color space transform capabilities of the display pipelines.

<div class="alert"><b>Note</b>  This field replaces the GammaRampCaps in the pre-WDDM 2.2 version of this structure.</div>
<div> </div>

### -field PresentationCaps

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a> structure that identifies the presentation capabilities, in bit-field flags, that the driver can support.


### -field MaxQueuedFlipOnVSync

[out] The number of flips that can be queued and pending at the graphics hardware. Each flip is latched to a digital-to-analog converter (DAC) at every VSync interrupt, in order, as the graphics hardware queues the flip.


### -field FlipCaps

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_flipcaps.md">DXGK_FLIPCAPS</a> structure that identifies the flipping capabilities, in bit-field flags, that the driver can support.


### -field SchedulingCaps

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md">DXGK_VIDSCHCAPS</a> structure that identifies the graphics processing unit (GPU) scheduling capabilities, in bit-field flags, that the driver can support.


### -field MemoryManagementCaps

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md">DXGK_VIDMMCAPS</a> structure that identifies the video memory management capabilities that the driver can support.


### -field GpuEngineTopology

[out] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gpuenginetopology.md">DXGK_GPUENGINETOPOLOGY</a> structure that describes the GPU-engine topology that the driver can support.


### -field WDDMVersion

[out] If a driver supports Windows 7 or later features (DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7), this member is reserved and should be set to zero.

<div class="alert"><b>Note</b>  <p class="note">If a driver does not support Windows 7 or later features (DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 7 WDK (Version 7600), set this member to DXGKDDI_WDDMv1.

<p class="note">If a driver does not support Windows 7 or later features (DXGKDDI_INTERFACE_VERSION &lt; DXGKDDI_INTERFACE_VERSION_WIN7), and you want to compile the driver
with the Windows 8 WDK, set this member to DXGKDDI_WDDMv1_2.

</div>

Supported starting with Windows 7.


### -field Reserved

Reserved.

### -field Reserved1

Reserved.

### -field PreemptionCaps

[out] A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_preemption_caps.md">D3DKMDT_PREEMPTION_CAPS</a> structure that describes the capabilities for the preemption of GPU graphics requests that the driver supports.

Supported starting with Windows 8.


### -field SupportNonVGA

[out] If <b>TRUE</b>, the driver supports resetting the  display device and releasing ownership of the current  power-on self-test (POST)  device by using the <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.

Supported starting with Windows 8.


### -field SupportSmoothRotation

[out] If <b>TRUE</b>, the driver supports updating path rotation on the adapter by using the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a> function, while not requiring a new VidPN to be created and set.

Supported starting with Windows 8.


### -field SupportPerEngineTDR

[out] If <b>TRUE</b>, the driver supports resetting individual GPU engines.

If this member is set, the display miniport driver must implement the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a>, and <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> functions.

Supported starting with Windows 8.


### -field SupportDirectFlip

[out] If <b>TRUE</b>, the driver supports the creation and opening of shared managed primary allocations. A value of <b>TRUE</b> also indicates the following:

<ul>
<li>The display miniport driver guarantees that when the <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function is called, the driver does not allow video memory to be flipped to an incompatible allocation.</li>
<li>The user mode driver validates Direct Flip resources before the Desktop Windows Manager (DWM) uses them.</li>
</ul>
Only the DWM can flip video memory to Direct Flip resources. The DWM validates these resources using the user-mode <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md">CheckDirectFlipSupport</a> function.

Supported starting with Windows 8.


### -field SupportMultiPlaneOverlay

[out] If <b>TRUE</b>, the display miniport driver supports multiplane overlays, and the driver should also set a value for the <b>MaxOverlayPlanes</b> member. If <b>FALSE</b>, the DirectX graphics kernel subsystem will not call multiplane overlay functions.

Supported starting with Windows 8.1.


### -field SupportRuntimePowerManagement

[out] If <b>TRUE</b>, the display miniport driver supports run-time power management.

If this member is set, the display miniport driver must implement the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a> and <a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a> functions.

Supported starting with Windows 8.


### -field SupportSurpriseRemovalInHibernation

[out] If <b>TRUE</b>, the display miniport driver supports cleaning up software resources after an external display device in hibernation mode is disconnected from the system.

If this member is set, the display miniport driver must implement the <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md">DxgkDdiNotifySurpriseRemoval</a> function with the <i>RemovalType</i> parameter set to <b>DxgkRemovalHibernation</b>.

For more information, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.

Supported starting with Windows 8.

### -field HybridDiscrete


[out] If <b>TRUE</b>, the display miniport driver is a discrete GPU in a <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">hybrid system</a>.

If this member is set, the display miniport driver should:<ul>
<li>support WDDM 1.3</li>
<li>support cross-adapter resources</li>
<li>have no display outputs</li>
</ul>


For more information, see <a href="https://msdn.microsoft.com/ECBB0AA7-50C2-41C8-9DC6-6EEFC5CEEB15">Using cross-adapter resources in a hybrid system</a>.

Supported starting with Windows 8.1.


### -field MaxOverlayPlanes

[out] If <b>SupportRuntimePowerManagement</b> is <b>TRUE</b>, the display miniport driver should set <b>MaxOverlayPlanes</b> to the maximum number of overlay planes that can be simultaneously displayed on a single output, including the primary surface, that it can support. If the number of available planes will change when the operating mode changes, the driver should use a number that reflects the best-case scenario.

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

Supports null context in DDI calls. When this value is set, the OS will pass NULL context in present related DDIs.

Supported starting in WDDM 2.4.

### -field MiscCaps.Detachable

Detachable, i.e. hot-pluggable. Drivers will set this bit during adapter initialization if the adapter is hot-pluggable.

### -field MiscCaps.VirtualGpuOnly

The adapter should not be used by Direct3D applications on the host.

### -field MiscCaps.Reserved

Reserved.

### -field MiscCaps.Value

## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidschcaps.md">DXGK_VIDSCHCAPS</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_checkdirectflipsupport.md">CheckDirectFlipSupport</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_pointerflags.md">DXGK_POINTERFLAGS</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_preemption_caps.md">D3DKMDT_PREEMPTION_CAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gammarampcaps.md">DXGK_GAMMARAMPCAPS</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_vidmmcaps.md">DXGK_VIDMMCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gpuenginetopology.md">DXGK_GPUENGINETOPOLOGY</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a>



<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a>



<a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md">DxgkDdiNotifySurpriseRemoval</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_flipcaps.md">DXGK_FLIPCAPS</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryadapterinfo.md">DXGKARG_QUERYADAPTERINFO</a>



 

 



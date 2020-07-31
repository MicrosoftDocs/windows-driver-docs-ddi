---
UID: NS:dispmprt._KMDDOD_INITIALIZATION_DATA
title: _KMDDOD_INITIALIZATION_DATA (dispmprt.h)
description: Contains pointers to functions implemented by a kernel mode display-only driver (KMDOD). The KMDOD's DriverEntry function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.
old-location: display\kmddod_initialization_data.htm
tech.root: display
ms.assetid: 04c1ece1-1c8f-40eb-8437-ac2fe1445095
ms.date: 05/10/2018
keywords: ["_KMDDOD_INITIALIZATION_DATA structure"]
ms.keywords: "*PKMDDOD_INITIALIZATION_DATA, KMDDOD_INITIALIZATION_DATA, KMDDOD_INITIALIZATION_DATA structure [Display Devices], PKMDDOD_INITIALIZATION_DATA, PKMDDOD_INITIALIZATION_DATA structure pointer [Display Devices], _KMDDOD_INITIALIZATION_DATA, display.kmddod_initialization_data, dispmprt/KMDDOD_INITIALIZATION_DATA, dispmprt/PKMDDOD_INITIALIZATION_DATA"
f1_keywords:
 - "dispmprt/KMDDOD_INITIALIZATION_DATA"
 - "KMDDOD_INITIALIZATION_DATA"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dispmprt.h
api_name:
- KMDDOD_INITIALIZATION_DATA
targetos: Windows
req.typenames: KMDDOD_INITIALIZATION_DATA, *PKMDDOD_INITIALIZATION_DATA
---

# _KMDDOD_INITIALIZATION_DATA structure


## -description


Contains pointers to functions implemented by a kernel mode display-only driver (KMDOD). The KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.


## -struct-fields




### -field Version

A positive integer that indicates the version of the functional interface implemented by the KMDOD. The KMDOD must set this member to <b>DXGKDDI_INTERFACE_VERSION</b>, which is defined in Dispmprt.h.


### -field DxgkDdiAddDevice

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_add_device">DxgkDdiAddDevice</a> function.


### -field DxgkDdiStartDevice

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.


### -field DxgkDdiStopDevice

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device">DxgkDdiStopDevice</a> function.


### -field DxgkDdiRemoveDevice

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_remove_device">DxgkDdiRemoveDevice</a> function.


### -field DxgkDdiDispatchIoRequest

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_dispatch_io_request">DxgkDdiDispatchIoRequest</a> function.


### -field DxgkDdiInterruptRoutine

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a> function.

<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div>
<div> </div>

### -field DxgkDdiDpcRoutine

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_dpc_routine">DxgkDdiDpcRoutine</a> function.

<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div>
<div> </div>

### -field DxgkDdiQueryChildRelations

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_relations">DxgkDdiQueryChildRelations</a> function.


### -field DxgkDdiQueryChildStatus

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_child_status">DxgkDdiQueryChildStatus</a> function.


### -field DxgkDdiQueryDeviceDescriptor

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_device_descriptor">DxgkDdiQueryDeviceDescriptor</a> function.


### -field DxgkDdiSetPowerState

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_set_power_state">DxgkDdiSetPowerState</a> function.


### -field DxgkDdiNotifyAcpiEvent

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_notify_acpi_event">DxgkDdiNotifyAcpiEvent</a> function.


### -field DxgkDdiResetDevice

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_reset_device">DxgkDdiResetDevice</a> function.


### -field DxgkDdiUnload

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_unload">DxgkDdiUnload</a> function.


### -field DxgkDdiQueryInterface

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_query_interface">DxgkDdiQueryInterface</a> function.


### -field DxgkDdiControlEtwLogging

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_control_etw_logging">DxgkDdiControlEtwLogging</a> function.


### -field DxgkDdiQueryAdapterInfo

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo">DxgkDdiQueryAdapterInfo</a> function.


### -field DxgkDdiSetPalette

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setpalette">DxgkDdiSetPalette</a> function that sets the palette for the display.


### -field DxgkDdiSetPointerPosition

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setpointerposition">DxgkDdiSetPointerPosition</a> function.


### -field DxgkDdiSetPointerShape

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setpointershape">DxgkDdiSetPointerShape</a> function.


### -field DxgkDdiEscape

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_escape">DxgkDdiEscape</a> function.


### -field DxgkDdiCollectDbgInfo

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_collectdbginfo">DxgkDdiCollectDbgInfo</a> function.


### -field DxgkDdiIsSupportedVidPn

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn">DxgkDdiIsSupportedVidPn</a> function.


### -field DxgkDdiRecommendFunctionalVidPn

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn">DxgkDdiRecommendFunctionalVidPn</a> function.


### -field DxgkDdiEnumVidPnCofuncModality

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality">DxgkDdiEnumVidPnCofuncModality</a> function.


### -field DxgkDdiSetVidPnSourceVisibility

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility">DxgkDdiSetVidPnSourceVisibility</a> function.


### -field DxgkDdiCommitVidPn

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn">DxgkDdiCommitVidPn</a>  function.


### -field DxgkDdiUpdateActiveVidPnPresentPath

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath">DxgkDdiUpdateActiveVidPnPresentPath</a> function.


### -field DxgkDdiRecommendMonitorModes

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_recommendmonitormodes">DxgkDdiRecommendMonitorModes</a> function.


### -field DxgkDdiGetScanLine

A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getscanline">DxgkDdiGetScanLine</a> function.

<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div>
<div> </div>

### -field DxgkDdiQueryVidPnHWCapability


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_queryvidpnhwcapability">DxgkDdiQueryVidPnHWCapability</a> function.


### -field DxgkDdiPresentDisplayOnly


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_presentdisplayonly">DxgkDdiPresentDisplayOnly</a> function.


### -field DxgkDdiStopDeviceAndReleasePostDisplayOwnership


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.


### -field DxgkDdiSystemDisplayEnable


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_system_display_enable">DxgkDdiSystemDisplayEnable</a> function.


### -field DxgkDdiSystemDisplayWrite


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_system_display_write">DxgkDdiSystemDisplayWrite</a> function.


### -field DxgkDdiGetChildContainerId


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_get_child_container_id">DxgkDdiGetChildContainerId</a> function.


### -field DxgkDdiControlInterrupt


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt">DxgkDdiControlInterrupt</a> function.

<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div>
<div> </div>

### -field DxgkDdiSetPowerComponentFState


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddisetpowercomponentfstate">DxgkDdiSetPowerComponentFState</a> function.


### -field DxgkDdiPowerRuntimeControlRequest


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddipowerruntimecontrolrequest">DxgkDdiPowerRuntimeControlRequest</a> function.


### -field DxgkDdiNotifySurpriseRemoval


A pointer to the KMDOD's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_notify_surprise_removal">DxgkDdiNotifySurpriseRemoval</a> function.


### -field DxgkDdiPowerRuntimeSetDeviceHandle

A pointer to the KMDOD's DxgkDdiPowerRuntimeSetDeviceHandle function.


## -remarks



If the kernel mode display-only driver (KMDOD) supports the VSync control feature, it must implement all of the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt">DxgkDdiControlInterrupt</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_getscanline">DxgkDdiGetScanLine</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_interrupt_routine">DxgkDdiInterruptRoutine</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_dpc_routine">DxgkDdiDpcRoutine</a>  functions and must provide valid function pointers to all of these functions in this structure. Conversely, if the KMDOD does not support the VSync control feature, it must not implement either <i>DxgkDdiControlInterrupt</i> or <i>DxgkDdiGetScanLine</i>  functions and must not provide valid function pointers to either of these functions in this structure. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/display/saving-energy-with-vsync-control">Saving Energy with VSync Control</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-display-miniport-driver">DriverEntry of Display Miniport Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nf-dispmprt-dxgkinitializedisplayonlydriver">DxgkInitializeDisplayOnlyDriver</a>
 

 


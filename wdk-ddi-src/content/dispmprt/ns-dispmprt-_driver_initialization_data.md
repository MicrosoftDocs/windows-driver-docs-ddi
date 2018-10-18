---
UID: NS:dispmprt._DRIVER_INITIALIZATION_DATA
title: "_DRIVER_INITIALIZATION_DATA"
author: windows-driver-content
description: The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver.
old-location: display\driver_initialization_data.htm
tech.root: display
ms.assetid: 3ab00f9c-7ce9-41bf-85c5-96be31d19719
ms.date: 5/10/2018
ms.keywords: "*PDRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA structure [Display Devices], DmStructs_7b91bf58-dfda-4c7c-ae26-21e577bdc152.xml, PDRIVER_INITIALIZATION_DATA, PDRIVER_INITIALIZATION_DATA structure pointer [Display Devices], _DRIVER_INITIALIZATION_DATA, display.driver_initialization_data, dispmprt/DRIVER_INITIALIZATION_DATA, dispmprt/PDRIVER_INITIALIZATION_DATA"
ms.topic: struct
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
-	Dispmprt.h
api_name:
-	DRIVER_INITIALIZATION_DATA
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INITIALIZATION_DATA, *PDRIVER_INITIALIZATION_DATA
---

# _DRIVER_INITIALIZATION_DATA structure


## -description


The <b>DRIVER_INITIALIZATION_DATA</b> structure contains pointers to functions implemented by the display miniport driver. The display miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.


## -struct-fields




### -field Version

A positive integer that indicates the version of the functional interface implemented by the display miniport driver. The display miniport driver must set this member to <b>DXGKDDI_INTERFACE_VERSION</b>, which is defined in Dispmprt.h.


### -field DxgkDdiAddDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -field DxgkDdiStartDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


### -field DxgkDdiStopDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a> function.


### -field DxgkDdiRemoveDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_remove_device.md">DxgkDdiRemoveDevice</a> function.


### -field DxgkDdiDispatchIoRequest

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dispatch_io_request.md">DxgkDdiDispatchIoRequest</a> function.


### -field DxgkDdiInterruptRoutine

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.


### -field DxgkDdiDpcRoutine

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a> function.


### -field DxgkDdiQueryChildRelations

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function.


### -field DxgkDdiQueryChildStatus

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a> function.


### -field DxgkDdiQueryDeviceDescriptor

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a> function.


### -field DxgkDdiSetPowerState

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a> function.


### -field DxgkDdiNotifyAcpiEvent

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a> function.


### -field DxgkDdiResetDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_reset_device.md">DxgkDdiResetDevice</a> function.


### -field DxgkDdiUnload

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_unload.md">DxgkDdiUnload</a> function.


### -field DxgkDdiQueryInterface

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function.


### -field DxgkDdiControlEtwLogging

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_control_etw_logging.md">DxgkDdiControlEtwLogging</a> function.


### -field DxgkDdiQueryAdapterInfo

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


### -field DxgkDdiCreateDevice

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function.


### -field DxgkDdiCreateAllocation

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function.


### -field DxgkDdiDestroyAllocation

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a> function.


### -field DxgkDdiDescribeAllocation

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_describeallocation.md">DxgkDdiDescribeAllocation</a> function.


### -field DxgkDdiGetStandardAllocationDriverData

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function.


### -field DxgkDdiAcquireSwizzlingRange

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function.


### -field DxgkDdiReleaseSwizzlingRange

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a> function.


### -field DxgkDdiPatch

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_patch.md">DxgkDdiPatch</a> function.


### -field DxgkDdiSubmitCommand

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function.


### -field DxgkDdiPreemptCommand

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_preemptcommand.md">DxgkDdiPreemptCommand</a> function.


### -field DxgkDdiBuildPagingBuffer

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_buildpagingbuffer.md">DxgkDdiBuildPagingBuffer</a> function.


### -field DxgkDdiSetPalette

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpalette.md">DxgkDdiSetPalette</a> function that sets the palette for the display.


### -field DxgkDdiSetPointerPosition

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a> function.


### -field DxgkDdiSetPointerShape

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointershape.md">DxgkDdiSetPointerShape</a> function.


### -field DxgkDdiResetFromTimeout

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetfromtimeout.md">DxgkDdiResetFromTimeout</a> function.


### -field DxgkDdiRestartFromTimeout

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_restartfromtimeout.md">DxgkDdiRestartFromTimeout</a> function.


### -field DxgkDdiEscape

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> function.


### -field DxgkDdiCollectDbgInfo

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a> function.


### -field DxgkDdiQueryCurrentFence

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querycurrentfence.md">DxgkDdiQueryCurrentFence</a> function.


### -field DxgkDdiIsSupportedVidPn

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a> function.


### -field DxgkDdiRecommendFunctionalVidPn

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function.


### -field DxgkDdiEnumVidPnCofuncModality

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function.


### -field DxgkDdiSetVidPnSourceAddress

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a> function.


### -field DxgkDdiSetVidPnSourceVisibility

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility.md">DxgkDdiSetVidPnSourceVisibility</a> function.


### -field DxgkDdiCommitVidPn

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>  function.


### -field DxgkDdiUpdateActiveVidPnPresentPath

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a> function.


### -field DxgkDdiRecommendMonitorModes

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a> function.


### -field DxgkDdiRecommendVidPnTopology

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendvidpntopology.md">DxgkDdiRecommendVidPnTopology</a> function.


### -field DxgkDdiGetScanLine

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getscanline.md">DxgkDdiGetScanLine</a> function.


### -field DxgkDdiStopCapture

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_stopcapture.md">DxgkDdiStopCapture</a> function.


### -field DxgkDdiControlInterrupt

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a> function.


### -field DxgkDdiCreateOverlay

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a> function.

<div class="alert"><b>Note</b>  The following 5 functions are specific to the graphics context device that was created through <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>:</div>
<div> </div>

### -field DxgkDdiDestroyDevice

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroydevice.md">DxgkDdiDestroyDevice</a> function.


### -field DxgkDdiOpenAllocation

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function.


### -field DxgkDdiCloseAllocation

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_closeallocation.md">DxgkDdiCloseAllocation</a> function.


### -field DxgkDdiRender

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_render.md">DxgkDdiRender</a> function.


### -field DxgkDdiPresent

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a> function.

<div class="alert"><b>Note</b>  The following 3 functions are specific to the overlay that was created through <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>:</div>
<div> </div>

### -field DxgkDdiUpdateOverlay

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateoverlay.md">DxgkDdiUpdateOverlay</a> function.


### -field DxgkDdiFlipOverlay

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_flipoverlay.md">DxgkDdiFlipOverlay</a> function.


### -field DxgkDdiDestroyOverlay

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyoverlay.md">DxgkDdiDestroyOverlay</a> function.

<div class="alert"><b>Note</b>  The following 2 functions are specific to supporting contexts:</div>
<div> </div>

### -field DxgkDdiCreateContext

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createcontext.md">DxgkDdiCreateContext</a> function.


### -field DxgkDdiDestroyContext

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroycontext.md">DxgkDdiDestroyContext</a> function.


### -field DxgkDdiLinkDevice

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_link_device.md">DxgkDdiLinkDevice</a> function. Be aware that this function is specific to supporting linked graphics adapters.


### -field DxgkDdiSetDisplayPrivateDriverFormat

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md">DxgkDdiSetDisplayPrivateDriverFormat</a> function.

<div class="alert"><b>Note</b>  The following 6 <a href="https://msdn.microsoft.com/F92F15A7-439D-4D45-84EE-A92D1E6AD779">reserved functions</a> declared in Dispmrt.h are available beginning with Windows 7:</div>
<div> </div>

### -field DxgkDdiDescribePageTable


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiUpdatePageTable


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiUpdatePageDirectory


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiMovePageDirectory


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiSubmitRender


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiCreateAllocation2


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

<div class="alert"><b>Note</b>  The following 3 functions are available beginning with Windows 7:</div>
<div> </div>

### -field DxgkDdiRenderKm


      A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_renderkm.md">DxgkDdiRenderKm</a> function.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field Reserved


      This member is reserved and should be set to zero.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.


### -field DxgkDdiQueryVidPnHWCapability


      A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a> function.


Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

<div class="alert"><b>Note</b>  The following 12 functions, including one reserved function, are available beginning with Windows 8:</div>
<div> </div>

### -field DxgkDdiSetPowerComponentFState

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a> function.

Supported starting with Windows 8.


### -field DxgkDdiQueryDependentEngineGroup

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_querydependentenginegroup.md">DxgkDdiQueryDependentEngineGroup</a> function.

Supported starting with Windows 8.


### -field DxgkDdiQueryEngineStatus

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryenginestatus.md">DxgkDdiQueryEngineStatus</a> function.

Supported starting with Windows 8.


### -field DxgkDdiResetEngine

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_resetengine.md">DxgkDdiResetEngine</a> function.

Supported starting with Windows 8.


### -field DxgkDdiStopDeviceAndReleasePostDisplayOwnership

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSystemDisplayEnable

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSystemDisplayWrite

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> function.

Supported starting with Windows 8.


### -field DxgkDdiCancelCommand

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_cancelcommand.md">DxgkDdiCancelCommand</a> function.

Supported starting with Windows 8.


### -field DxgkDdiGetChildContainerId

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_get_child_container_id.md">DxgkDdiGetChildContainerId</a> function.

Supported starting with Windows 8.


### -field DxgkDdiPowerRuntimeControlRequest

A pointer to the display miniport driver's <a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a> function.

Supported starting with Windows 8.


### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiNotifySurpriseRemoval

A pointer to the display miniport driver's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md">DxgkDdiNotifySurpriseRemoval</a> function.

Supported starting with Windows 8.


### -field DxgkDdiGetNodeMetadata

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getnodemetadata.md">DxgkDdiGetNodeMetadata</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiSetPowerPState

This member is reserved and should be set to zero.

Supported starting with Windows 8.1.


### -field DxgkDdiControlInterrupt2

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt2.md">DxgkDdiControlInterrupt2</a> function.

Supported starting with Windows 10


### -field DxgkDdiCheckMultiPlaneOverlaySupport

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport.md">DxgkDdiCheckMultiPlaneOverlaySupport</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiCalibrateGpuClock

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_calibrategpuclock.md">DxgkDdiCalibrateGpuClock</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiFormatHistoryBuffer

A pointer to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_formathistorybuffer.md">DxgkDdiFormatHistoryBuffer</a> function.

Supported starting with Windows 8.1.


### -field DxgkDdiRenderGdi


A pointer to the [DxgkDdiRenderGdi](../d3dkmddi/nc-d3dkmddi-dxgkddi_rendergdi.md) callback function.

### -field DxgkDdiSubmitCommandVirtual


A pointer to the [DXGKDDI_SUBMITCOMMANDVIRTUAL](..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommandvirtual.md) callback function.

### -field DxgkDdiSetRootPageTable


A pointer to the [DXGKDDI_SETROOTPAGETABLE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setrootpagetable.md) callback function.

### -field DxgkDdiGetRootPageTableSize


A pointer to the [DXGKDDI_GETROOTPAGETABLESIZE](../d3dkmddi/nc-d3dkmddi-dxgkddi_getrootpagetablesize.md) callback function.

### -field DxgkDdiMapCpuHostAperture


A pointer to the [DXGKDDI_MAPCPUHOSTAPERTURE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_mapcpuhostaperture.md) callback function.

### -field DxgkDdiUnmapCpuHostAperture


A pointer to the [DXGKDDI_UNMAPCPUHOSTAPERTURE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_unmapcpuhostaperture.md) callback function.

### -field DxgkDdiCheckMultiPlaneOverlaySupport2


A pointer to the [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2](..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md) callback function.

### -field DxgkDdiCreateProcess


A pointer to the [DXGKDDI_CREATEPROCESS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprocess.md) callback function.

### -field DxgkDdiDestroyProcess


A pointer to the [DXGKDDI_DESTROYPROCESS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyprocess.md) callback function.

### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2


A pointer to the [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md) callback function.

### -field Reserved1

Reserved.


### -field Reserved2

Reserved.


### -field DxgkDdiPowerRuntimeSetDeviceHandle


A pointer to the DXGKDDI_POWERRUNTIMESETDEVICEHANDLE callback function.

### -field DxgkDdiSetStablePowerState


A pointer to the DXGKDDI_SETSTABLEPOWERSTATE callback function.

### -field DxgkDdiSetVideoProtectedRegion


A pointer to the DXGKDDI_SETVIDEOPROTECTEDREGION callback function.

### -field DxgkDdiCheckMultiPlaneOverlaySupport3


A pointer to the [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3](..\d3dkmddi\nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md) callback function.

### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3


A pointer to the [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) callback function.

### -field DxgkDdiPostMultiPlaneOverlayPresent


A pointer to the [DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT](..\d3dkmddi\nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) callback function.

### -field DxgkDdiValidateUpdateAllocationProperty


A pointer to the DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY callback function.

### -field DxgkDdiControlModeBehavior

A pointer to the DXGKDDI_CONTROLMODEBEHAVIOR callback function.


### -field DxgkDdiUpdateMonitorLinkInfo

A pointer to the [DXGKDDI_UPDATEMONITORLINKINFO](..\d3dkmddi\nc-d3dkmddi-dxgkddi_updatemonitorlinkinfo.md) callback function.


### -field DxgkDdiCreateHwContext


A pointer to the DXGKDDI_CREATEHWCONTEXT callback function.

### -field DxgkDdiDestroyHwContext


A pointer to the DXGKDDI_DESTROYHWCONTEXT callback function.

### -field DxgkDdiCreateHwQueue

A pointer to the DXGKDDI_CREATEHWQUEUE callback function.


### -field DxgkDdiDestroyHwQueue


A pointer to the DXGKDDI_DESTROYHWQUEUE callback function.

### -field DxgkDdiSubmitCommandToHwQueue


A pointer to the [DXGKDDI_SUBMITCOMMANDTOHWQUEUE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md) callback function.

### -field DxgkDdiSwitchToHwContextList


A pointer to the [DXGKDDI_SWITCHTOHWCONTEXTLIST](..\d3dkmddi\nc-d3dkmddi-dxgkddi_switchtohwcontextlist.md) callback function.

### -field DxgkDdiResetHwEngine




### -field DxgkDdiCreatePeriodicFrameNotification


A pointer to the [DXGKDDI_CREATEPERIODICFRAMENOTIFICATION](..\d3dkmddi\nc-d3dkmddi-dxgkddi_createperiodicframenotification.md) callback function.

### -field DxgkDdiDestroyPeriodicFrameNotification


A pointer to the [DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION](..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyperiodicframenotification.md) callback function.

### -field DxgkDdiSetTimingsFromVidPn


A pointer to the [DXGKDDI_SETTIMINGSFROMVIDPN](..\d3dkmddi\nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) callback function.

### -field DxgkDdiSetTargetGamma


A pointer to the [DXGKDDI_SETTARGETGAMMA](..\d3dkmddi\nc-d3dkmddi-dxgkddi_settargetgamma.md) callback function.

### -field DxgkDdiSetTargetContentType


A pointer to the [DXGKDDI_SETTARGETCONTENTTYPE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_settargetcontenttype.md) callback function.

### -field DxgkDdiSetTargetAnalogCopyProtection


A pointer to the [DXGKDDI_SETTARGETANALOGCOPYPROTECTION](..\d3dkmddi\nc-d3dkmddi-dxgkddi_settargetanalogcopyprotection.md) callback function.

### -field DxgkDdiSetTargetAdjustedColorimetry


A pointer to the [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY](..\dispmprt\nc-dispmprt-dxgkddi_settargetadjustedcolorimetry.md) callback function.

### -field DxgkDdiDisplayDetectControl


A pointer to the [DXGKDDI_DISPLAYDETECTCONTROL](..\d3dkmddi\nc-d3dkmddi-dxgkddi_displaydetectcontrol.md) callback function.

### -field DxgkDdiQueryConnectionChange


A pointer to the [DXGKDDI_QUERYCONNECTIONCHANGE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryconnectionchange.md) callback function.

### -field DxgkDdiExchangePreStartInfo


A pointer to the [DXGKDDI_EXCHANGEPRESTARTINFO](..\dispmprt\nc-dispmprt-dxgkddi_exchangeprestartinfo.md) callback function.

### -field DxgkDdiGetMultiPlaneOverlayCaps


A pointer to the [DXGKDDI_GETMULTIPLANEOVERLAYCAPS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_getmultiplaneoverlaycaps.md) callback function.

### -field DxgkDdiGetPostCompositionCaps


A pointer to the [DXGKDDI_GETPOSTCOMPOSITIONCAPS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_getpostcompositioncaps.md) callback function.

### -field DxgkDdiUpdateHwContextState


A pointer to the [DXGKDDI_UPDATEHWCONTEXTSTATE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_updatehwcontextstate.md) callback function.

### -field DxgkDdiCreateProtectedSession

A pointer to the [DXGKDDI_CREATEPROTECTEDSESSION](..\d3dkmddi\nc-d3dkmddi-dxgkddi_createprotectedsession.md) callback function.


### -field DxgkDdiDestroyProtectedSession

A pointer to the [DXGKDDI_DESTROYPROTECTEDSESSION](..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyprotectedsession.md) callback function.

### -field DxgkDdiSetSchedulingLogBuffer

A pointer to the [DXGKDDI_SETSCHEDULINGLOGBUFFER](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setschedulinglogbuffer.md) callback function.

### -field DxgkDdiSetupPriorityBands

A pointer to the [DXGKDDI_SETUPPRIORITYBANDS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setupprioritybands.md) callback function.

### -field DxgkDdiNotifyFocusPresent

A pointer to the [DXGKDDI_NOTIFYFOCUSPRESENT](..\d3dkmddi\nc-d3dkmddi-dxgkddi_notifyfocuspresent.md) callback function.

### -field DxgkDdiSetContextSchedulingProperties

A pointer to the [DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setcontextschedulingproperties.md) callback function.

### -field DxgkDdiSuspendContext

A pointer to the [DXGKDDI_SUSPENDCONTEXT](..\d3dkmddi\nc-d3dkmddi-dxgkddi_suspendcontext.md) callback function.

### -field DxgkDdiResumeContext

A pointer to the [DXGKDDI_RESUMECONTEXT](..\d3dkmddi\nc-d3dkmddi-dxgkddi_resumecontext.md) callback function.

### -field DxgkDdiSetVirtualMachineData

A pointer to the [DXGKDDI_SETVIRTUALMACHINEDATA](..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md) callback function.

### -field DxgkDdiBeginExclusiveAccess

A pointer to the [DXGKDDI_BEGINEXCLUSIVEACCESS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_beginexclusiveaccess.md) callback function.

### -field DxgkDdiEndExclusiveAccess

A pointer to the [DXGKDDI_ENDEXCLUSIVEACCESS](..\d3dkmddi\nc-d3dkmddi-dxgkddi_endexclusiveaccess.md) callback function.

### -field DxgkDdiQueryDiagnosticTypesSupport

A pointer to the [DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT](..\dispmprt\nc-dispmprt-dxgkddi_querydiagnostictypessupport.md) callback function.

### -field DxgkDdiControlDiagnosticReporting

A pointer to the [DXGKDDI_CONTROLDIAGNOSTICREPORTING](..\dispmprt\nc-dispmprt-dxgkddi_controldiagnosticreporting.md) callback function.

### -field DxgkDdiResumeHwEngine
 
A pointer to the [DXGKDDI_RESUMEHWENGINE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_resumehwengine.md) callback function.

### -field DxgkDdiSignalMonitoredFence

Pointer to a [DxgkDdiSignalMonitoredFence](../d3dkmddi/nc-d3dkmddi-dxgkddi_signalmonitoredfence.md), called to add a GPU instruction to signal the paging monitored fence object to the DMA (direct memory access) buffer.

### -field DxgkDdiPresentToHwQueue

A pointer to the [DXGKDDI_PRESENTTOHWQUEUE](..\d3dkmddi\nc-d3dkmddi-dxgkddi_presenttohwqueue.md) callback function.

### -field DxgkDdiValidateSubmitCommand

A pointer to the [DXGKDDI_VALIDATESUBMITCOMMAND](..\d3dkmddi\nc-d3dkmddi-dxgkddi_validatesubmitcommand.md) callback function.

### -field DxgkDdiSetTargetAdjustedColorimetry2

A pointer to the [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2](../dispmprt/nc-dispmprt-dxgkddi_settargetadjustedcolorimetry2.md) callback function.

### -field DxgkDdiSetTrackedWorkloadPowerLevel

A pointer to the [DxgkDdiSetTrackedWorkloadPowerLevel](../d3dkmddi/nc-d3dkmddi-dxgkddi_settrackedworkloadpowerlevel.md) callback function.


## -remarks



The following <b>typedef</b> declarations provide function data types from data types that are dereferenced pointers to functions:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef DXGKDDI_ADD_DEVICE  *PDXGKDDI_ADD_DEVICE;
typedef DXGKDDI_START_DEVICE  *PDXGKDDI_START_DEVICE;
typedef DXGKDDI_STOP_DEVICE  *PDXGKDDI_STOP_DEVICE;
typedef DXGKDDI_REMOVE_DEVICE  *PDXGKDDI_REMOVE_DEVICE;
typedef DXGKDDI_DISPATCH_IO_REQUEST  *PDXGKDDI_DISPATCH_IO_REQUEST;
typedef DXGKDDI_QUERY_CHILD_RELATIONS  *PDXGKDDI_QUERY_CHILD_RELATIONS;
typedef DXGKDDI_QUERY_CHILD_STATUS  *PDXGKDDI_QUERY_CHILD_STATUS;
typedef DXGKDDI_INTERRUPT_ROUTINE  *PDXGKDDI_INTERRUPT_ROUTINE;
typedef DXGKDDI_DPC_ROUTINE  *PDXGKDDI_DPC_ROUTINE;
typedef DXGKDDI_QUERY_DEVICE_DESCRIPTOR  *PDXGKDDI_QUERY_DEVICE_DESCRIPTOR;
typedef DXGKDDI_SET_POWER_STATE  *PDXGKDDI_SET_POWER_STATE;
typedef DXGKDDI_NOTIFY_ACPI_EVENT  *PDXGKDDI_NOTIFY_ACPI_EVENT;
typedef DXGKDDI_RESET_DEVICE  *PDXGKDDI_RESET_DEVICE;
typedef DXGKDDI_UNLOAD  *PDXGKDDI_UNLOAD;
typedef DXGKDDI_QUERY_INTERFACE  *PDXGKDDI_QUERY_INTERFACE;
typedef DXGKDDI_CONTROL_ETW_LOGGING  *PDXGKDDI_CONTROL_ETW_LOGGING;
typedef DXGKDDI_QUERYADAPTERINFO  *PDXGKDDI_QUERYADAPTERINFO;
typedef DXGKDDI_CREATEDEVICE  *PDXGKDDI_CREATEDEVICE;
typedef DXGKDDI_CREATEALLOCATION  *PDXGKDDI_CREATEALLOCATION;
typedef DXGKDDI_DESTROYALLOCATION  *PDXGKDDI_DESTROYALLOCATION;
typedef DXGKDDI_DESCRIBEALLOCATION  *PDXGKDDI_DESCRIBEALLOCATION;
typedef DXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA  *PDXGKDDI_GETSTANDARDALLOCATIONDRIVERDATA;
typedef DXGKDDI_ACQUIRESWIZZLINGRANGE  *PDXGKDDI_ACQUIRESWIZZLINGRANGE;
typedef DXGKDDI_RELEASESWIZZLINGRANGE  *PDXGKDDI_RELEASESWIZZLINGRANGE;
typedef DXGKDDI_PATCH  *PDXGKDDI_PATCH;
typedef DXGKDDI_SUBMITCOMMAND  *PDXGKDDI_SUBMITCOMMAND;
typedef DXGKDDI_PREEMPTCOMMAND  *PDXGKDDI_PREEMPTCOMMAND;
typedef DXGKDDI_BUILDPAGINGBUFFER  *PDXGKDDI_BUILDPAGINGBUFFER;
typedef DXGKDDI_SETPALETTE  *PDXGKDDI_SETPALETTE;
typedef DXGKDDI_SETPOINTERPOSITION  *PDXGKDDI_SETPOINTERPOSITION;
typedef DXGKDDI_SETPOINTERSHAPE  *PDXGKDDI_SETPOINTERSHAPE;
typedef DXGKDDI_RESETFROMTIMEOUT  *PDXGKDDI_RESETFROMTIMEOUT;
typedef DXGKDDI_RESTARTFROMTIMEOUT  *PDXGKDDI_RESTARTFROMTIMEOUT;
typedef DXGKDDI_ESCAPE  *PDXGKDDI_ESCAPE;
typedef DXGKDDI_COLLECTDBGINFO  *PDXGKDDI_COLLECTDBGINFO;
typedef DXGKDDI_QUERYCURRENTFENCE  *PDXGKDDI_QUERYCURRENTFENCE;
typedef DXGKDDI_ISSUPPORTEDVIDPN  *PDXGKDDI_ISSUPPORTEDVIDPN;
typedef DXGKDDI_RECOMMENDFUNCTIONALVIDPN  *PDXGKDDI_RECOMMENDFUNCTIONALVIDPN;
typedef DXGKDDI_ENUMVIDPNCOFUNCMODALITY  *PDXGKDDI_ENUMVIDPNCOFUNCMODALITY;
typedef DXGKDDI_SETVIDPNSOURCEADDRESS  *PDXGKDDI_SETVIDPNSOURCEADDRESS;
typedef DXGKDDI_SETVIDPNSOURCEVISIBILITY  *PDXGKDDI_SETVIDPNSOURCEVISIBILITY;
typedef DXGKDDI_COMMITVIDPN  *PDXGKDDI_COMMITVIDPN;
typedef DXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH  *PDXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH;
typedef DXGKDDI_RECOMMENDMONITORMODES  *PDXGKDDI_RECOMMENDMONITORMODES;
typedef DXGKDDI_RECOMMENDVIDPNTOPOLOGY  *PDXGKDDI_RECOMMENDVIDPNTOPOLOGY;
typedef DXGKDDI_GETSCANLINE  *PDXGKDDI_GETSCANLINE;
typedef DXGKDDI_STOPCAPTURE  *PDXGKDDI_STOPCAPTURE;
typedef DXGKDDI_CONTROLINTERRUPT  *PDXGKDDI_CONTROLINTERRUPT;
typedef DXGKDDI_CREATEOVERLAY  *PDXGKDDI_CREATEOVERLAY;
typedef DXGKDDI_DESTROYDEVICE  *PDXGKDDI_DESTROYDEVICE;
typedef DXGKDDI_OPENALLOCATIONINFO  *PDXGKDDI_OPENALLOCATIONINFO;
typedef DXGKDDI_CLOSEALLOCATION  *PDXGKDDI_CLOSEALLOCATION;
typedef DXGKDDI_RENDER  *PDXGKDDI_RENDER;
typedef DXGKDDI_PRESENT  *PDXGKDDI_PRESENT;
typedef DXGKDDI_UPDATEOVERLAY  *PDXGKDDI_UPDATEOVERLAY;
typedef DXGKDDI_FLIPOVERLAY  *PDXGKDDI_FLIPOVERLAY;
typedef DXGKDDI_DESTROYOVERLAY  *PDXGKDDI_DESTROYOVERLAY;
typedef DXGKDDI_CREATECONTEXT  *PDXGKDDI_CREATECONTEXT;
typedef DXGKDDI_DESTROYCONTEXT  *PDXGKDDI_DESTROYCONTEXT;
typedef DXGKDDI_LINK_DEVICE  *PDXGKDDI_LINK_DEVICE;
typedef DXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT  *PDXGKDDI_SETDISPLAYPRIVATEDRIVERFORMAT;
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN7)
typedef DXGKDDI_DESCRIBEPAGETABLE  *PDXGKDDI_DESCRIBEPAGETABLE;
typedef DXGKDDI_UPDATEPAGETABLE  *PDXGKDDI_UPDATEPAGETABLE;
typedef DXGKDDI_UPDATEPAGEDIRECTORY  *PDXGKDDI_UPDATEPAGEDIRECTORY;
typedef DXGKDDI_MOVEPAGEDIRECTORY  *PDXGKDDI_MOVEPAGEDIRECTORY;
typedef DXGKDDI_SUBMITRENDER  *PDXGKDDI_SUBMITRENDER;
typedef DXGKDDI_CREATEALLOCATION2  *PDXGKDDI_CREATEALLOCATION2;
typedef DXGKDDI_RENDERKM  *PDXGKDDI_RENDERKM;
typedef DXGKDDI_QUERYVIDPNHWCAPABILITY  *PDXGKDDI_QUERYVIDPNHWCAPABILITY;
#endif // DXGKDDI_INTERFACE_VERSION_WIN7
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WIN8)
typedef DXGKDDISETPOWERCOMPONENTFSTATE  *PDXGKDDISETPOWERCOMPONENTFSTATE;
typedef DXGKDDI_QUERYDEPENDENTENGINEGROUP  *PDXGKDDI_QUERYDEPENDENTENGINEGROUP;
typedef DXGKDDI_QUERYENGINESTATUS  *PDXGKDDI_QUERYENGINESTATUS;
typedef DXGKDDI_RESETENGINE  *PDXGKDDI_RESETENGINE;
typedef DXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP  *PDXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP;
typedef DXGKDDI_SYSTEM_DISPLAY_ENABLE  *PDXGKDDI_SYSTEM_DISPLAY_ENABLE;
typedef DXGKDDI_SYSTEM_DISPLAY_WRITE  *PDXGKDDI_SYSTEM_DISPLAY_WRITE;
typedef DXGKDDI_CANCELCOMMAND  *PDXGKDDI_CANCELCOMMAND;
typedef DXGKDDI_GET_CHILD_CONTAINER_ID  *PDXGKDDI_GET_CHILD_CONTAINER_ID;
typedef DXGKDDIPOWERRUNTIMECONTROLREQUEST  *PDXGKDDIPOWERRUNTIMECONTROLREQUEST;
typedef DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY *PDXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY;
typedef DXGKDDI_NOTIFY_SURPRISE_REMOVAL         *PDXGKDDI_NOTIFY_SURPRISE_REMOVAL;
#endif //
#if (DXGKDDI_INTERFACE_VERSION &gt;= DXGKDDI_INTERFACE_VERSION_WDDM1_3)
typedef DXGKDDI_GETNODEMETADATA  *PDXGKDDI_GETNODEMETADATA;
typedef DXGKDDI_CONTROLINTERRUPT2  *PDXGKDDI_CONTROLINTERRUPT2;
typedef DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT  *PDXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT;
typedef DXGKDDI_FORMATHISTORYBUFFER  *PDXGKDDI_FORMATHISTORYBUFFER;
typedef DXGKDDI_CALIBRATEGPUCLOCK  *PDXGKDDI_CALIBRATEGPUCLOCK;
#endif</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>



 

 



---
UID: NS:dispmprt._DRIVER_INITIALIZATION_DATA
title: DRIVER_INITIALIZATION_DATA (dispmprt.h)
description: The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver.
old-location: display\driver_initialization_data.htm
tech.root: display
ms.date: 05/31/2022
keywords: ["DRIVER_INITIALIZATION_DATA structure"]
ms.keywords: "*PDRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA, DRIVER_INITIALIZATION_DATA structure [Display Devices], DmStructs_7b91bf58-dfda-4c7c-ae26-21e577bdc152.xml, PDRIVER_INITIALIZATION_DATA, PDRIVER_INITIALIZATION_DATA structure pointer [Display Devices], _DRIVER_INITIALIZATION_DATA, display.driver_initialization_data, dispmprt/DRIVER_INITIALIZATION_DATA, dispmprt/PDRIVER_INITIALIZATION_DATA"
req.header: dispmprt.h
req.include-header: Dispmprt.h
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
req.typenames: DRIVER_INITIALIZATION_DATA, *PDRIVER_INITIALIZATION_DATA
f1_keywords:
 - _DRIVER_INITIALIZATION_DATA
 - dispmprt/_DRIVER_INITIALIZATION_DATA
 - PDRIVER_INITIALIZATION_DATA
 - dispmprt/PDRIVER_INITIALIZATION_DATA
 - DRIVER_INITIALIZATION_DATA
 - dispmprt/DRIVER_INITIALIZATION_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Dispmprt.h
api_name:
 - _DRIVER_INITIALIZATION_DATA
 - PDRIVER_INITIALIZATION_DATA
 - DRIVER_INITIALIZATION_DATA
---

# DRIVER_INITIALIZATION_DATA structure

## -description

The DRIVER_INITIALIZATION_DATA structure contains pointers to functions implemented by the display miniport driver. The display miniport driver's [**DriverEntry**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver) function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.

## -struct-fields

### -field Version

A positive integer that indicates the version of the functional interface implemented by the display miniport driver. The display miniport driver must set this member to **DXGKDDI_INTERFACE_VERSION**, which is defined in *Dispmprt.h*.

### -field DxgkDdiAddDevice

A pointer to the display miniport driver's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function.

### -field DxgkDdiStartDevice

A pointer to the display miniport driver's [**DxgkDdiStartDevice**](nc-dispmprt-dxgkddi_start_device.md) function.

### -field DxgkDdiStopDevice

A pointer to the display miniport driver's [**DxgkDdiStopDevice**](nc-dispmprt-dxgkddi_stop_device.md) function.

### -field DxgkDdiRemoveDevice

A pointer to the display miniport driver's [**DxgkDdiRemoveDevice**](nc-dispmprt-dxgkddi_remove_device.md) function.

### -field DxgkDdiDispatchIoRequest

A pointer to the display miniport driver's [**DxgkDdiDispatchIoRequest**](nc-dispmprt-dxgkddi_dispatch_io_request.md) function.

### -field DxgkDdiInterruptRoutine

A pointer to the display miniport driver's [**DxgkDdiInterruptRoutine**](nc-dispmprt-dxgkddi_interrupt_routine.md) function.

### -field DxgkDdiDpcRoutine

A pointer to the display miniport driver's [**DxgkDdiDpcRoutine**](nc-dispmprt-dxgkddi_dpc_routine.md) function.

### -field DxgkDdiQueryChildRelations

A pointer to the display miniport driver's [**DxgkDdiQueryChildRelations**](nc-dispmprt-dxgkddi_query_child_relations.md) function.

### -field DxgkDdiQueryChildStatus

A pointer to the display miniport driver's [**DxgkDdiQueryChildStatus**](nc-dispmprt-dxgkddi_query_child_status.md) function.

### -field DxgkDdiQueryDeviceDescriptor

A pointer to the display miniport driver's [**DxgkDdiQueryDeviceDescriptor**](nc-dispmprt-dxgkddi_query_device_descriptor.md) function.

### -field DxgkDdiSetPowerState

A pointer to the display miniport driver's [**DxgkDdiSetPowerState**](nc-dispmprt-dxgkddi_set_power_state.md) function.

### -field DxgkDdiNotifyAcpiEvent

A pointer to the display miniport driver's [**DxgkDdiNotifyAcpiEvent**](nc-dispmprt-dxgkddi_notify_acpi_event.md) function.

### -field DxgkDdiResetDevice

A pointer to the display miniport driver's [**DxgkDdiResetDevice**](nc-dispmprt-dxgkddi_reset_device.md) function.

### -field DxgkDdiUnload

A pointer to the display miniport driver's [**DxgkDdiUnload**](nc-dispmprt-dxgkddi_unload.md) function.

### -field DxgkDdiQueryInterface

A pointer to the display miniport driver's [**DxgkDdiQueryInterface**](nc-dispmprt-dxgkddi_query_interface.md) function.

### -field DxgkDdiControlEtwLogging

A pointer to the display miniport driver's [**DxgkDdiControlEtwLogging**](nc-dispmprt-dxgkddi_control_etw_logging.md) function.

### -field DxgkDdiQueryAdapterInfo

A pointer to the display miniport driver's [**DxgkDdiQueryAdapterInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryadapterinfo.md) function.

### -field DxgkDdiCreateDevice

A pointer to the display miniport driver's [**DxgkDdiCreateDevice**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice.md) function.

### -field DxgkDdiCreateAllocation

A pointer to the display miniport driver's [**DxgkDdiCreateAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation.md) function.

### -field DxgkDdiDestroyAllocation

A pointer to the display miniport driver's [**DxgkDdiDestroyAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroyallocation.md) function.

### -field DxgkDdiDescribeAllocation

A pointer to the display miniport driver's [**DxgkDdiDescribeAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_describeallocation.md) function.

### -field DxgkDdiGetStandardAllocationDriverData

A pointer to the display miniport driver's [**DxgkDdiGetStandardAllocationDriverData**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md) function.

### -field DxgkDdiAcquireSwizzlingRange

A pointer to the display miniport driver's [**DxgkDdiAcquireSwizzlingRange**](../d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md) function.

### -field DxgkDdiReleaseSwizzlingRange

A pointer to the display miniport driver's [**DxgkDdiReleaseSwizzlingRange**](../d3dkmddi/nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md) function.

### -field DxgkDdiPatch

A pointer to the display miniport driver's [**DxgkDdiPatch**](../d3dkmddi/nc-d3dkmddi-dxgkddi_patch.md) function.

### -field DxgkDdiSubmitCommand

A pointer to the display miniport driver's [**DxgkDdiSubmitCommand**](../d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand.md) function.

### -field DxgkDdiPreemptCommand

A pointer to the display miniport driver's [**DxgkDdiPreemptCommand**](../d3dkmddi/nc-d3dkmddi-dxgkddi_preemptcommand.md) function.

### -field DxgkDdiBuildPagingBuffer

A pointer to the display miniport driver's [**DxgkDdiBuildPagingBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_buildpagingbuffer.md) function.

### -field DxgkDdiSetPalette

A pointer to the display miniport driver's [**DxgkDdiSetPalette**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setpalette.md) function that sets the palette for the display.

### -field DxgkDdiSetPointerPosition

A pointer to the display miniport driver's [**DxgkDdiSetPointerPosition**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setpointerposition.md) function.

### -field DxgkDdiSetPointerShape

A pointer to the display miniport driver's [**DxgkDdiSetPointerShape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setpointershape.md) function.

### -field DxgkDdiResetFromTimeout

A pointer to the display miniport driver's [**DxgkDdiResetFromTimeout**](../d3dkmddi/nc-d3dkmddi-dxgkddi_resetfromtimeout.md) function.

### -field DxgkDdiRestartFromTimeout

A pointer to the display miniport driver's [**DxgkDdiRestartFromTimeout**](../d3dkmddi/nc-d3dkmddi-dxgkddi_restartfromtimeout.md) function.

### -field DxgkDdiEscape

A pointer to the display miniport driver's [**DxgkDdiEscape**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md) function.

### -field DxgkDdiCollectDbgInfo

A pointer to the display miniport driver's [**DxgkDdiCollectDbgInfo**](../d3dkmddi/nc-d3dkmddi-dxgkddi_collectdbginfo.md) function.

### -field DxgkDdiQueryCurrentFence

A pointer to the display miniport driver's [**DxgkDdiQueryCurrentFence**](../d3dkmddi/nc-d3dkmddi-dxgkddi_querycurrentfence.md) function.

### -field DxgkDdiIsSupportedVidPn

A pointer to the display miniport driver's [**DxgkDdiIsSupportedVidPn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_issupportedvidpn.md) function.

### -field DxgkDdiRecommendFunctionalVidPn

A pointer to the display miniport driver's [**DxgkDdiRecommendFunctionalVidPn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md) function.

### -field DxgkDdiEnumVidPnCofuncModality

A pointer to the display miniport driver's [**DxgkDdiEnumVidPnCofuncModality**](../d3dkmddi/nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md) function.

### -field DxgkDdiSetVidPnSourceAddress

A pointer to the display miniport driver's [**DxgkDdiSetVidPnSourceAddress**](/previous-versions/windows/hardware/drivers/ff560767(v=vs.85)) function.

### -field DxgkDdiSetVidPnSourceVisibility

A pointer to the display miniport driver's [**DxgkDdiSetVidPnSourceVisibility**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility.md) function.

### -field DxgkDdiCommitVidPn

A pointer to the display miniport driver's [**DxgkDdiCommitVidPn**](../d3dkmddi/nc-d3dkmddi-dxgkddi_commitvidpn.md) function.

### -field DxgkDdiUpdateActiveVidPnPresentPath

A pointer to the display miniport driver's [**DxgkDdiUpdateActiveVidPnPresentPath**](../d3dkmddi/nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md) function.

### -field DxgkDdiRecommendMonitorModes

A pointer to the display miniport driver's [**DxgkDdiRecommendMonitorModes**](../d3dkmddi/nc-d3dkmddi-dxgkddi_recommendmonitormodes.md) function.

### -field DxgkDdiRecommendVidPnTopology

A pointer to the display miniport driver's [**DxgkDdiRecommendVidPnTopology**](../d3dkmddi/nc-d3dkmddi-dxgkddi_recommendvidpntopology.md) function.

### -field DxgkDdiGetScanLine

A pointer to the display miniport driver's [**DxgkDdiGetScanLine**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getscanline.md) function.

### -field DxgkDdiStopCapture

A pointer to the display miniport driver's [**DxgkDdiStopCapture**](../d3dkmddi/nc-d3dkmddi-dxgkddi_stopcapture.md) function.

### -field DxgkDdiControlInterrupt

A pointer to the display miniport driver's [**DxgkDdiControlInterrupt**](../d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt.md) function.

### -field DxgkDdiCreateOverlay

A pointer to the display miniport driver's [**DxgkDdiCreateOverlay**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay.md) function.

> [!NOTE]
> The following functions are specific to the graphics context device that was created through [**DxgkDdiCreateDevice**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice.md):

### -field DxgkDdiDestroyDevice

A pointer to the display miniport driver's [**DxgkDdiDestroyDevice**](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroydevice.md) function.

### -field DxgkDdiOpenAllocation

A pointer to the display miniport driver's [**DxgkDdiOpenAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_openallocationinfo.md) function.

### -field DxgkDdiCloseAllocation

A pointer to the display miniport driver's [**DxgkDdiCloseAllocation**](../d3dkmddi/nc-d3dkmddi-dxgkddi_closeallocation.md) function.

### -field DxgkDdiRender

A pointer to the display miniport driver's [**DxgkDdiRender**](../d3dkmddi/nc-d3dkmddi-dxgkddi_render.md) function.

### -field DxgkDdiPresent

A pointer to the display miniport driver's [**DxgkDdiPresent**](../d3dkmddi/nc-d3dkmddi-dxgkddi_present.md) function.

> [!NOTE]
> The following functions are specific to the overlay that was created through [DxgkDdiCreateOverlay](../d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay.md):

### -field DxgkDdiUpdateOverlay

A pointer to the display miniport driver's [**DxgkDdiUpdateOverlay**](../d3dkmddi/nc-d3dkmddi-dxgkddi_updateoverlay.md) function.

### -field DxgkDdiFlipOverlay

A pointer to the display miniport driver's [**DxgkDdiFlipOverlay**](../d3dkmddi/nc-d3dkmddi-dxgkddi_flipoverlay.md) function.

### -field DxgkDdiDestroyOverlay

A pointer to the display miniport driver's [**DxgkDdiDestroyOverlay**](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroyoverlay.md) function.

> [!NOTE]
> The following functions are specific to supporting contexts:

### -field DxgkDdiCreateContext

A pointer to the display miniport driver's [**DxgkDdiCreateContext**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createcontext.md) function.

### -field DxgkDdiDestroyContext

A pointer to the display miniport driver's [**DxgkDdiDestroyContext**](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroycontext.md) function.

### -field DxgkDdiLinkDevice

A pointer to the display miniport driver's [**DxgkDdiLinkDevice**](nc-dispmprt-dxgkddi_link_device.md) function. Be aware that this function is specific to supporting linked graphics adapters.

### -field DxgkDdiSetDisplayPrivateDriverFormat

A pointer to the display miniport driver's [**DxgkDdiSetDisplayPrivateDriverFormat**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setdisplayprivatedriverformat.md) function.

> [!NOTE]
> The following [reserved functions](/windows-hardware/drivers/display/dispmprt-h---reserved) declared in *dispmrt.h* are available beginning with Windows 7:

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

> [!NOTE]
> The following functions are available beginning with Windows 7:

### -field DxgkDdiRenderKm

A pointer to the display miniport driver's [**DxgkDdiRenderKm**](../d3dkmddi/nc-d3dkmddi-dxgkddi_renderkm.md) function.

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

### -field Reserved

This member is reserved and should be set to zero.

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

### -field DxgkDdiQueryVidPnHWCapability

A pointer to the display miniport driver's [**DxgkDdiQueryVidPnHWCapability**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md) function.

Available only when DXGKDDI_INTERFACE_VERSION ≥ DXGKDDI_INTERFACE_VERSION_WIN7.

> [!NOTE]
> The following functions are available beginning with Windows 8:

### -field DxgkDdiSetPowerComponentFState

A pointer to the display miniport driver's [**DxgkDdiSetPowerComponentFState**](../d3dkmddi/nc-d3dkmddi-dxgkddisetpowercomponentfstate.md) function.

Supported starting with Windows 8.

### -field DxgkDdiQueryDependentEngineGroup

A pointer to the display miniport driver's [**DxgkDdiQueryDependentEngineGroup**](../d3dkmddi/nc-d3dkmddi-dxgkddi_querydependentenginegroup.md) function.

Supported starting with Windows 8.

### -field DxgkDdiQueryEngineStatus

A pointer to the display miniport driver's [**DxgkDdiQueryEngineStatus**](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryenginestatus.md) function.

Supported starting with Windows 8.

### -field DxgkDdiResetEngine

A pointer to the display miniport driver's [**DxgkDdiResetEngine**](../d3dkmddi/nc-d3dkmddi-dxgkddi_resetengine.md) function.

Supported starting with Windows 8.

### -field DxgkDdiStopDeviceAndReleasePostDisplayOwnership

A pointer to the display miniport driver's [**DxgkDdiStopDeviceAndReleasePostDisplayOwnership**](nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md) function.

Supported starting with Windows 8.

### -field DxgkDdiSystemDisplayEnable

A pointer to the display miniport driver's [**DxgkDdiSystemDisplayEnable**](nc-dispmprt-dxgkddi_system_display_enable.md) function.

Supported starting with Windows 8.

### -field DxgkDdiSystemDisplayWrite

A pointer to the display miniport driver's [**DxgkDdiSystemDisplayWrite**](nc-dispmprt-dxgkddi_system_display_write.md) function.

Supported starting with Windows 8.

### -field DxgkDdiCancelCommand

A pointer to the display miniport driver's [**DxgkDdiCancelCommand**](../d3dkmddi/nc-d3dkmddi-dxgkddi_cancelcommand.md) function.

Supported starting with Windows 8.

### -field DxgkDdiGetChildContainerId

A pointer to the display miniport driver's [**DxgkDdiGetChildContainerId**](nc-dispmprt-dxgkddi_get_child_container_id.md) function.

Supported starting with Windows 8.

### -field DxgkDdiPowerRuntimeControlRequest

A pointer to the display miniport driver's [**DxgkDdiPowerRuntimeControlRequest**](../d3dkmddi/nc-d3dkmddi-dxgkddipowerruntimecontrolrequest.md) function.

Supported starting with Windows 8.

### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay

A pointer to the display miniport driver's [**DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay**](../d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md) function.

Supported starting with Windows 8.1.

### -field DxgkDdiNotifySurpriseRemoval

A pointer to the display miniport driver's [**DxgkDdiNotifySurpriseRemoval**](nc-dispmprt-dxgkddi_notify_surprise_removal.md) function.

Supported starting with Windows 8.

### -field DxgkDdiGetNodeMetadata

A pointer to the display miniport driver's [**DxgkDdiGetNodeMetadata**](../d3dkmddi/nc-d3dkmddi-dxgkddi_getnodemetadata.md) function.

Supported starting with Windows 8.1.

### -field DxgkDdiSetPowerPState

This member is reserved and should be set to zero.

Supported starting with Windows 8.1.

### -field DxgkDdiControlInterrupt2

A pointer to the display miniport driver's [**DxgkDdiControlInterrupt2**](../d3dkmddi/nc-d3dkmddi-dxgkddi_controlinterrupt2.md) function.

Supported starting with Windows 10

### -field DxgkDdiCheckMultiPlaneOverlaySupport

A pointer to the display miniport driver's [**DxgkDdiCheckMultiPlaneOverlaySupport**](../d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport.md) function.

Supported starting with Windows 8.1.

### -field DxgkDdiCalibrateGpuClock

A pointer to the display miniport driver's [**DxgkDdiCalibrateGpuClock**](../d3dkmddi/nc-d3dkmddi-dxgkddi_calibrategpuclock.md) function.

Supported starting with Windows 8.1.

### -field DxgkDdiFormatHistoryBuffer

A pointer to the display miniport driver's [**DxgkDdiFormatHistoryBuffer**](../d3dkmddi/nc-d3dkmddi-dxgkddi_formathistorybuffer.md) function.

Supported starting with Windows 8.1.

### -field DxgkDdiRenderGdi

A pointer to the [DxgkDdiRenderGdi](../d3dkmddi/nc-d3dkmddi-dxgkddi_rendergdi.md) callback function.

### -field DxgkDdiSubmitCommandVirtual

A pointer to the [DXGKDDI_SUBMITCOMMANDVIRTUAL](../d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommandvirtual.md) callback function.

### -field DxgkDdiSetRootPageTable

A pointer to the [DXGKDDI_SETROOTPAGETABLE](../d3dkmddi/nc-d3dkmddi-dxgkddi_setrootpagetable.md) callback function.

### -field DxgkDdiGetRootPageTableSize

A pointer to the [DXGKDDI_GETROOTPAGETABLESIZE](../d3dkmddi/nc-d3dkmddi-dxgkddi_getrootpagetablesize.md) callback function.

### -field DxgkDdiMapCpuHostAperture

A pointer to the [DXGKDDI_MAPCPUHOSTAPERTURE](../d3dkmddi/nc-d3dkmddi-dxgkddi_mapcpuhostaperture.md) callback function.

### -field DxgkDdiUnmapCpuHostAperture

A pointer to the [DXGKDDI_UNMAPCPUHOSTAPERTURE](../d3dkmddi/nc-d3dkmddi-dxgkddi_unmapcpuhostaperture.md) callback function.

### -field DxgkDdiCheckMultiPlaneOverlaySupport2

A pointer to the [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT2](../d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport2.md) callback function.

### -field DxgkDdiCreateProcess

A pointer to the [DXGKDDI_CREATEPROCESS](../d3dkmddi/nc-d3dkmddi-dxgkddi_createprocess.md) callback function.

### -field DxgkDdiDestroyProcess

A pointer to the [DXGKDDI_DESTROYPROCESS](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroyprocess.md) callback function.

### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2

A pointer to the [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY2](../d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2.md) callback function.

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

A pointer to the [DXGKDDI_CHECKMULTIPLANEOVERLAYSUPPORT3](../d3dkmddi/nc-d3dkmddi-dxgkddi_checkmultiplaneoverlaysupport3.md) callback function.

### -field DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay3

A pointer to the [DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY3](../d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay3.md) callback function.

### -field DxgkDdiPostMultiPlaneOverlayPresent

A pointer to the [DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT](../d3dkmddi/nc-d3dkmddi-dxgkddi_postmultiplaneoverlaypresent.md) callback function.

### -field DxgkDdiValidateUpdateAllocationProperty

A pointer to the DXGKDDI_VALIDATEUPDATEALLOCATIONPROPERTY callback function.

### -field DxgkDdiControlModeBehavior

A pointer to the [DXGKDDI_CONTROLMODEBEHAVIOR](../d3dkmddi/nc-d3dkmddi-dxgkddi_controlmodebehavior.md) callback function.

### -field DxgkDdiUpdateMonitorLinkInfo

A pointer to the [DXGKDDI_UPDATEMONITORLINKINFO](../d3dkmddi/nc-d3dkmddi-dxgkddi_updatemonitorlinkinfo.md) callback function.

### -field DxgkDdiCreateHwContext

A pointer to the DXGKDDI_CREATEHWCONTEXT callback function.

### -field DxgkDdiDestroyHwContext

A pointer to the DXGKDDI_DESTROYHWCONTEXT callback function.

### -field DxgkDdiCreateHwQueue

A pointer to the DXGKDDI_CREATEHWQUEUE callback function.

### -field DxgkDdiDestroyHwQueue

A pointer to the DXGKDDI_DESTROYHWQUEUE callback function.

### -field DxgkDdiSubmitCommandToHwQueue

A pointer to the [DXGKDDI_SUBMITCOMMANDTOHWQUEUE](../d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommandtohwqueue.md) callback function.

### -field DxgkDdiSwitchToHwContextList

A pointer to the [DXGKDDI_SWITCHTOHWCONTEXTLIST](../d3dkmddi/nc-d3dkmddi-dxgkddi_switchtohwcontextlist.md) callback function.

### -field DxgkDdiResetHwEngine

### -field DxgkDdiCreatePeriodicFrameNotification

A pointer to the [DXGKDDI_CREATEPERIODICFRAMENOTIFICATION](../d3dkmddi/nc-d3dkmddi-dxgkddi_createperiodicframenotification.md) callback function.

### -field DxgkDdiDestroyPeriodicFrameNotification

A pointer to the [DXGKDDI_DESTROYPERIODICFRAMENOTIFICATION](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroyperiodicframenotification.md) callback function.

### -field DxgkDdiSetTimingsFromVidPn

A pointer to the [DXGKDDI_SETTIMINGSFROMVIDPN](../d3dkmddi/nc-d3dkmddi-dxgkddi_settimingsfromvidpn.md) callback function.

### -field DxgkDdiSetTargetGamma

A pointer to the [DXGKDDI_SETTARGETGAMMA](../d3dkmddi/nc-d3dkmddi-dxgkddi_settargetgamma.md) callback function.

### -field DxgkDdiSetTargetContentType

A pointer to the [DXGKDDI_SETTARGETCONTENTTYPE](../d3dkmddi/nc-d3dkmddi-dxgkddi_settargetcontenttype.md) callback function.

### -field DxgkDdiSetTargetAnalogCopyProtection

A pointer to the [DXGKDDI_SETTARGETANALOGCOPYPROTECTION](../d3dkmddi/nc-d3dkmddi-dxgkddi_settargetanalogcopyprotection.md) callback function.

### -field DxgkDdiSetTargetAdjustedColorimetry

A pointer to the [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY](../dispmprt/nc-dispmprt-dxgkddi_settargetadjustedcolorimetry.md) callback function.

### -field DxgkDdiDisplayDetectControl

A pointer to the [DXGKDDI_DISPLAYDETECTCONTROL](../d3dkmddi/nc-d3dkmddi-dxgkddi_displaydetectcontrol.md) callback function.

### -field DxgkDdiQueryConnectionChange

A pointer to the [DXGKDDI_QUERYCONNECTIONCHANGE](../d3dkmddi/nc-d3dkmddi-dxgkddi_queryconnectionchange.md) callback function.

### -field DxgkDdiExchangePreStartInfo

A pointer to the [DXGKDDI_EXCHANGEPRESTARTINFO](../dispmprt/nc-dispmprt-dxgkddi_exchangeprestartinfo.md) callback function.

### -field DxgkDdiGetMultiPlaneOverlayCaps

A pointer to the [DXGKDDI_GETMULTIPLANEOVERLAYCAPS](../d3dkmddi/nc-d3dkmddi-dxgkddi_getmultiplaneoverlaycaps.md) callback function.

### -field DxgkDdiGetPostCompositionCaps

A pointer to the [DXGKDDI_GETPOSTCOMPOSITIONCAPS](../d3dkmddi/nc-d3dkmddi-dxgkddi_getpostcompositioncaps.md) callback function.

### -field DxgkDdiUpdateHwContextState

A pointer to the [DXGKDDI_UPDATEHWCONTEXTSTATE](../d3dkmddi/nc-d3dkmddi-dxgkddi_updatehwcontextstate.md) callback function.

### -field DxgkDdiCreateProtectedSession

A pointer to the [DXGKDDI_CREATEPROTECTEDSESSION](../d3dkmddi/nc-d3dkmddi-dxgkddi_createprotectedsession.md) callback function.

### -field DxgkDdiDestroyProtectedSession

A pointer to the [DXGKDDI_DESTROYPROTECTEDSESSION](../d3dkmddi/nc-d3dkmddi-dxgkddi_destroyprotectedsession.md) callback function.

### -field DxgkDdiSetSchedulingLogBuffer

A pointer to the [DXGKDDI_SETSCHEDULINGLOGBUFFER](../d3dkmddi/nc-d3dkmddi-dxgkddi_setschedulinglogbuffer.md) callback function.

### -field DxgkDdiSetupPriorityBands

A pointer to the [DXGKDDI_SETUPPRIORITYBANDS](../d3dkmddi/nc-d3dkmddi-dxgkddi_setupprioritybands.md) callback function.

### -field DxgkDdiNotifyFocusPresent

A pointer to the [DXGKDDI_NOTIFYFOCUSPRESENT](../d3dkmddi/nc-d3dkmddi-dxgkddi_notifyfocuspresent.md) callback function.

### -field DxgkDdiSetContextSchedulingProperties

A pointer to the [DXGKDDI_SETCONTEXTSCHEDULINGPROPERTIES](../d3dkmddi/nc-d3dkmddi-dxgkddi_setcontextschedulingproperties.md) callback function.

### -field DxgkDdiSuspendContext

A pointer to the [DXGKDDI_SUSPENDCONTEXT](../d3dkmddi/nc-d3dkmddi-dxgkddi_suspendcontext.md) callback function.

### -field DxgkDdiResumeContext

A pointer to the [DXGKDDI_RESUMECONTEXT](../d3dkmddi/nc-d3dkmddi-dxgkddi_resumecontext.md) callback function.

### -field DxgkDdiSetVirtualMachineData

A pointer to the [DXGKDDI_SETVIRTUALMACHINEDATA](../d3dkmddi/nc-d3dkmddi-dxgkddi_setvirtualmachinedata.md) callback function.

### -field DxgkDdiBeginExclusiveAccess

A pointer to the [DXGKDDI_BEGINEXCLUSIVEACCESS](../d3dkmddi/nc-d3dkmddi-dxgkddi_beginexclusiveaccess.md) callback function.

### -field DxgkDdiEndExclusiveAccess

A pointer to the [DXGKDDI_ENDEXCLUSIVEACCESS](../d3dkmddi/nc-d3dkmddi-dxgkddi_endexclusiveaccess.md) callback function.

### -field DxgkDdiQueryDiagnosticTypesSupport

A pointer to the [DXGKDDI_QUERYDIAGNOSTICTYPESSUPPORT](../dispmprt/nc-dispmprt-dxgkddi_querydiagnostictypessupport.md) callback function.

### -field DxgkDdiControlDiagnosticReporting

A pointer to the [DXGKDDI_CONTROLDIAGNOSTICREPORTING](../dispmprt/nc-dispmprt-dxgkddi_controldiagnosticreporting.md) callback function.

### -field DxgkDdiResumeHwEngine

A pointer to the [DXGKDDI_RESUMEHWENGINE](../d3dkmddi/nc-d3dkmddi-dxgkddi_resumehwengine.md) callback function.

### -field DxgkDdiSignalMonitoredFence

Pointer to a [DxgkDdiSignalMonitoredFence](../d3dkmddi/nc-d3dkmddi-dxgkddi_signalmonitoredfence.md), called to add a GPU instruction to signal the paging monitored fence object to the DMA (direct memory access) buffer.

### -field DxgkDdiPresentToHwQueue

A pointer to the [DXGKDDI_PRESENTTOHWQUEUE](../d3dkmddi/nc-d3dkmddi-dxgkddi_presenttohwqueue.md) callback function.

### -field DxgkDdiValidateSubmitCommand

A pointer to the [DXGKDDI_VALIDATESUBMITCOMMAND](../d3dkmddi/nc-d3dkmddi-dxgkddi_validatesubmitcommand.md) callback function.

### -field DxgkDdiSetTargetAdjustedColorimetry2

A pointer to the [DXGKDDI_SETTARGETADJUSTEDCOLORIMETRY2](../dispmprt/nc-dispmprt-dxgkddi_settargetadjustedcolorimetry2.md) callback function.

### -field DxgkDdiSetTrackedWorkloadPowerLevel

A pointer to the [DxgkDdiSetTrackedWorkloadPowerLevel](../d3dkmddi/nc-d3dkmddi-dxgkddi_settrackedworkloadpowerlevel.md) callback function.

### -field DxgkDdiSaveMemoryForHotUpdate

A pointer to the [DxgkDdiSaveMemoryForHotUpdate](../d3dkmddi/nc-d3dkmddi-dxgkcb_savememoryforhotupdate.md) callback function.

### -field DxgkDdiRestoreMemoryForHotUpdate

A pointer to the [DxgkDdiRestoreMemoryForHotUpdate](../d3dkmddi/nc-d3dkmddi-dxgkddi_restorememoryforhotupdate.md) callback function.

### -field DxgkDdiCollectDiagnosticInfo

A pointer to the [DxgkDdiCollectDiagnosticInfo](nc-dispmprt-dxgkddi_collectdiagnosticinfo.md) callback function.

### -field Reserved3

Reserved.

### -field DxgkDdiControlInterrupt3

A pointer to the **DxgkDdiControlInterrupt3** callback function.

### -field DxgkDdiSetFlipQueueLogBuffer

A pointer to the **DxgkDdiSetFlipQueueLogBuffer** callback function.

### -field DxgkDdiUpdateFlipQueueLog

A pointer to the **DxgkDdiUpdateFlipQueueLog** callback function.

### -field DxgkDdiCancelQueuedFlips

A pointer to the **DxgkDdiCancelQueuedFlips** callback function.

### -field DxgkDdiSetInterruptTargetPresentId

A pointer to the **DxgkDdiSetInterruptTargetPresentId** callback function.

### -field DxgkDdiSetAllocationBackingStore

A pointer to the **DxgkDdiSetAllocationBackingStore** callback function.

### -field DxgkDdiCreateCpuEvent

A pointer to the **DxgkDdiCreateCpuEvent** callback function.

### -field DxgkDdiDestroyCpuEvent

A pointer to the **DxgkDdiDestroyCpuEvent** callback function.

### -field DxgkDdiCancelFlips

A pointer to the **DxgkDdiCancelFlips** callback function.

### -field DxgkDdiCreateNativeFence

A pointer to the **DxgkDdiCreateNativeFence** callback function.

### -field DxgkDdiDestroyNativeFence

A pointer to the **DxgkDdiDestroyNativeFence** callback function.

### -field DxgkDdiUpdateMonitoredValues

A pointer to the **DxgkDdiUpdateMonitoredValues** callback function.

### -field DxgkDdiNotifyCurrentValueUpdates

A pointer to the **DxgkDdiNotifyCurrentValueUpdates** callback function.

### -field DxgkDdiCreateDoorbell

A pointer to the **DxgkDdiCreateDoorbell** callback function.

### -field DxgkDdiConnectDoorbell

A pointer to the **DxgkDdiConnectDoorbell** callback function.

### -field DxgkDdiDisconnectDoorbell

A pointer to the **DxgkDdiDisconnectDoorbell** callback function.

### -field DxgkDdiDestroyDoorbell

A pointer to the **DxgkDdiDestroyDoorbell** callback function.

### -field DxgkDdiNotifyWorkSubmission

A pointer to the **DxgkDdiNotifyWorkSubmission** callback function.

### -field DxgkDdiFlushHwQueue

A pointer to the **DxgkDdiFlushHwQueue** callback function.

## -see-also

[**DriverEntry of Display Miniport Driver**](/windows-hardware/drivers/display/driverentry-of-display-miniport-driver)

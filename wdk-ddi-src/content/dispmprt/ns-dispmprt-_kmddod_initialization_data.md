---
UID: NS:dispmprt._KMDDOD_INITIALIZATION_DATA
title: "_KMDDOD_INITIALIZATION_DATA"
author: windows-driver-content
description: Contains pointers to functions implemented by a kernel mode display-only driver (KMDOD). The KMDOD's DriverEntry function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.
old-location: display\kmddod_initialization_data.htm
old-project: display
ms.assetid: 04c1ece1-1c8f-40eb-8437-ac2fe1445095
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dispmprt/KMDDOD_INITIALIZATION_DATA, KMDDOD_INITIALIZATION_DATA, KMDDOD_INITIALIZATION_DATA structure [Display Devices], PKMDDOD_INITIALIZATION_DATA structure pointer [Display Devices], display.kmddod_initialization_data, dispmprt/PKMDDOD_INITIALIZATION_DATA, *PKMDDOD_INITIALIZATION_DATA, PKMDDOD_INITIALIZATION_DATA, _KMDDOD_INITIALIZATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Dispmprt.h
apiname:
-	KMDDOD_INITIALIZATION_DATA
product: Windows
targetos: Windows
req.typenames: "*PKMDDOD_INITIALIZATION_DATA, KMDDOD_INITIALIZATION_DATA"
---

# _KMDDOD_INITIALIZATION_DATA structure


## -description


Contains pointers to functions implemented by a kernel mode display-only driver (KMDOD). The KMDOD's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function provides the Microsoft DirectX graphics kernel subsystem with entry points by filling in the members of this structure.


## -syntax


````
typedef struct _KMDDOD_INITIALIZATION_DATA {
  ULONG                                                   Version;
  PDXGKDDI_ADD_DEVICE                                     DxgkDdiAddDevice;
  PDXGKDDI_START_DEVICE                                   DxgkDdiStartDevice;
  PDXGKDDI_STOP_DEVICE                                    DxgkDdiStopDevice;
  PDXGKDDI_REMOVE_DEVICE                                  DxgkDdiRemoveDevice;
  PDXGKDDI_DISPATCH_IO_REQUEST                            DxgkDdiDispatchIoRequest;
  PDXGKDDI_INTERRUPT_ROUTINE                              DxgkDdiInterruptRoutine;
  PDXGKDDI_DPC_ROUTINE                                    DxgkDdiDpcRoutine;
  PDXGKDDI_QUERY_CHILD_RELATIONS                          DxgkDdiQueryChildRelations;
  PDXGKDDI_QUERY_CHILD_STATUS                             DxgkDdiQueryChildStatus;
  PDXGKDDI_QUERY_DEVICE_DESCRIPTOR                        DxgkDdiQueryDeviceDescriptor;
  PDXGKDDI_SET_POWER_STATE                                DxgkDdiSetPowerState;
  PDXGKDDI_NOTIFY_ACPI_EVENT                              DxgkDdiNotifyAcpiEvent;
  PDXGKDDI_RESET_DEVICE                                   DxgkDdiResetDevice;
  PDXGKDDI_UNLOAD                                         DxgkDdiUnload;
  PDXGKDDI_QUERY_INTERFACE                                DxgkDdiQueryInterface;
  PDXGKDDI_CONTROL_ETW_LOGGING                            DxgkDdiControlEtwLogging;
  PDXGKDDI_QUERYADAPTERINFO                               DxgkDdiQueryAdapterInfo;
  PDXGKDDI_SETPALETTE                                     DxgkDdiSetPalette;
  PDXGKDDI_SETPOINTERPOSITION                             DxgkDdiSetPointerPosition;
  PDXGKDDI_SETPOINTERSHAPE                                DxgkDdiSetPointerShape;
  PDXGKDDI_ESCAPE                                         DxgkDdiEscape;
  PDXGKDDI_COLLECTDBGINFO                                 DxgkDdiCollectDbgInfo;
  PDXGKDDI_ISSUPPORTEDVIDPN                               DxgkDdiIsSupportedVidPn;
  PDXGKDDI_RECOMMENDFUNCTIONALVIDPN                       DxgkDdiRecommendFunctionalVidPn;
  PDXGKDDI_ENUMVIDPNCOFUNCMODALITY                        DxgkDdiEnumVidPnCofuncModality;
  PDXGKDDI_SETVIDPNSOURCEVISIBILITY                       DxgkDdiSetVidPnSourceVisibility;
  PDXGKDDI_COMMITVIDPN                                    DxgkDdiCommitVidPn;
  PDXGKDDI_UPDATEACTIVEVIDPNPRESENTPATH                   DxgkDdiUpdateActiveVidPnPresentPath;
  PDXGKDDI_RECOMMENDMONITORMODES                          DxgkDdiRecommendMonitorModes;
  PDXGKDDI_GETSCANLINE                                    DxgkDdiGetScanLine;
  PDXGKDDI_QUERYVIDPNHWCAPABILITY                         DxgkDdiQueryVidPnHWCapability;
  PDXGKDDI_PRESENTDISPLAYONLY                             DxgkDdiPresentDisplayOnly;
  PDXGKDDI_STOP_DEVICE_AND_RELEASE_POST_DISPLAY_OWNERSHIP DxgkDdiStopDeviceAndReleasePostDisplayOwnership;
  PDXGKDDI_SYSTEM_DISPLAY_ENABLE                          DxgkDdiSystemDisplayEnable;
  PDXGKDDI_SYSTEM_DISPLAY_WRITE                           DxgkDdiSystemDisplayWrite;
  PDXGKDDI_GET_CHILD_CONTAINER_ID                         DxgkDdiGetChildContainerId;
  PDXGKDDI_CONTROLINTERRUPT                               DxgkDdiControlInterrupt;
  PDXGKDDISETPOWERCOMPONENTFSTATE                         DxgkDdiSetPowerComponentFState;
  PDXGKDDIPOWERRUNTIMECONTROLREQUEST                      DxgkDdiPowerRuntimeControlRequest;
  PDXGKDDI_NOTIFY_SURPRISE_REMOVAL                        DxgkDdiNotifySurpriseRemoval;
} KMDDOD_INITIALIZATION_DATA, *PKMDDOD_INITIALIZATION_DATA;
````


## -struct-fields




#### - Version

A positive integer that indicates the version of the functional interface implemented by the KMDOD. The KMDOD must set this member to <b>DXGKDDI_INTERFACE_VERSION</b>, which is defined in Dispmprt.h.


#### - DxgkDdiAddDevice

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


#### - DxgkDdiStartDevice

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.


#### - DxgkDdiStopDevice

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device.md">DxgkDdiStopDevice</a> function.


#### - DxgkDdiRemoveDevice

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_remove_device.md">DxgkDdiRemoveDevice</a> function.


#### - DxgkDdiDispatchIoRequest

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dispatch_io_request.md">DxgkDdiDispatchIoRequest</a> function.


#### - DxgkDdiInterruptRoutine

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a> function.
<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div><div> </div>

#### - DxgkDdiDpcRoutine

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a> function.
<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div><div> </div>

#### - DxgkDdiQueryChildRelations

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_relations.md">DxgkDdiQueryChildRelations</a> function.


#### - DxgkDdiQueryChildStatus

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_child_status.md">DxgkDdiQueryChildStatus</a> function.


#### - DxgkDdiQueryDeviceDescriptor

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_device_descriptor.md">DxgkDdiQueryDeviceDescriptor</a> function.


#### - DxgkDdiSetPowerState

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_set_power_state.md">DxgkDdiSetPowerState</a> function.


#### - DxgkDdiNotifyAcpiEvent

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_acpi_event.md">DxgkDdiNotifyAcpiEvent</a> function.


#### - DxgkDdiResetDevice

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_reset_device.md">DxgkDdiResetDevice</a> function.


#### - DxgkDdiUnload

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_unload.md">DxgkDdiUnload</a> function.


#### - DxgkDdiQueryInterface

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_query_interface.md">DxgkDdiQueryInterface</a> function.


#### - DxgkDdiControlEtwLogging

A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_control_etw_logging.md">DxgkDdiControlEtwLogging</a> function.


#### - DxgkDdiQueryAdapterInfo

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryadapterinfo.md">DxgkDdiQueryAdapterInfo</a> function.


#### - DxgkDdiSetPalette

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpalette.md">DxgkDdiSetPalette</a> function that sets the palette for the display.


#### - DxgkDdiSetPointerPosition

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointerposition.md">DxgkDdiSetPointerPosition</a> function.


#### - DxgkDdiSetPointerShape

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setpointershape.md">DxgkDdiSetPointerShape</a> function.


#### - DxgkDdiEscape

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_escape.md">DxgkDdiEscape</a> function.


#### - DxgkDdiCollectDbgInfo

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_collectdbginfo.md">DxgkDdiCollectDbgInfo</a> function.


#### - DxgkDdiIsSupportedVidPn

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_issupportedvidpn.md">DxgkDdiIsSupportedVidPn</a> function.


#### - DxgkDdiRecommendFunctionalVidPn

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendfunctionalvidpn.md">DxgkDdiRecommendFunctionalVidPn</a> function.


#### - DxgkDdiEnumVidPnCofuncModality

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a> function.


#### - DxgkDdiSetVidPnSourceVisibility

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourcevisibility.md">DxgkDdiSetVidPnSourceVisibility</a> function.


#### - DxgkDdiCommitVidPn

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>  function.


#### - DxgkDdiUpdateActiveVidPnPresentPath

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a> function.


#### - DxgkDdiRecommendMonitorModes

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a> function.


#### - DxgkDdiGetScanLine

A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getscanline.md">DxgkDdiGetScanLine</a> function.
<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div><div> </div>

#### - DxgkDdiQueryVidPnHWCapability


      A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a> function.


#### - DxgkDdiPresentDisplayOnly


      A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_queryvidpnhwcapability.md">DxgkDdiQueryVidPnHWCapability</a> function.


#### - DxgkDdiStopDeviceAndReleasePostDisplayOwnership


      A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_stop_device_and_release_post_display_ownership.md">DxgkDdiStopDeviceAndReleasePostDisplayOwnership</a> function.


#### - DxgkDdiSystemDisplayEnable


      A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_enable.md">DxgkDdiSystemDisplayEnable</a> function.


#### - DxgkDdiSystemDisplayWrite


      A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_system_display_write.md">DxgkDdiSystemDisplayWrite</a> function.


#### - DxgkDdiGetChildContainerId


      A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_get_child_container_id.md">DxgkDdiGetChildContainerId</a> function.


#### - DxgkDdiControlInterrupt


      A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a> function.
<div class="alert"><b>Note</b>  This function pointer has special requirements. For more information, see Remarks.</div><div> </div>

#### - DxgkDdiSetPowerComponentFState


      A pointer to the KMDOD's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddisetpowercomponentfstate.md">DxgkDdiSetPowerComponentFState</a> function.


#### - DxgkDdiPowerRuntimeControlRequest


      A pointer to the KMDOD's <a href="https://msdn.microsoft.com/56535128-3107-4fb5-b0e1-2e913c386cc2">DxgkDdiPowerRuntimeControlRequest</a> function.


#### - DxgkDdiNotifySurpriseRemoval


      A pointer to the KMDOD's <a href="..\dispmprt\nc-dispmprt-dxgkddi_notify_surprise_removal.md">DxgkDdiNotifySurpriseRemoval</a> function.


### -field DxgkDdiPowerRuntimeSetDeviceHandle

 



## -remarks


If the kernel mode display-only driver (KMDOD) supports the VSync control feature, it must implement all of the  <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_controlinterrupt.md">DxgkDdiControlInterrupt</a>, <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getscanline.md">DxgkDdiGetScanLine</a>, <a href="..\dispmprt\nc-dispmprt-dxgkddi_interrupt_routine.md">DxgkDdiInterruptRoutine</a>, and <a href="..\dispmprt\nc-dispmprt-dxgkddi_dpc_routine.md">DxgkDdiDpcRoutine</a>  functions and must provide valid function pointers to all of these functions in this structure. Conversely, if the KMDOD does not support the VSync control feature, it must not implement either <i>DxgkDdiControlInterrupt</i> or <i>DxgkDdiGetScanLine</i>  functions and must not provide valid function pointers to either of these functions in this structure. For more information, see <a href="https://msdn.microsoft.com/d7ee7461-0d2a-4103-9225-57ca10a75a7a">Saving Energy with VSync Control</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556157">DriverEntry of Display Miniport Driver</a>

<a href="..\dispmprt\nf-dispmprt-dxgkinitializedisplayonlydriver.md">DxgkInitializeDisplayOnlyDriver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20KMDDOD_INITIALIZATION_DATA structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NC:fwpsk.FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0
title: FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 (fwpsk.h)
description: The filter engine calls the vSwitchRuntimeStateSaveNotifyFn (FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0) callout function to notify a callout driver about virtual switch run-time state save events.Note  FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 is a specific version of FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK. See WFP Version-Independent Names and Targeting Specific Versions of Windows for more information.
old-location: netvista\fwps_vswitch_runtime_state_save_callback0.htm
tech.root: netvista
ms.assetid: 2CDD666F-3D88-4078-9A4C-D7A107806EA7
ms.date: 05/02/2018
keywords: ["FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 callback function"]
ms.keywords: FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0, FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 callback, fwpsk/vSwitchRuntimeStateSaveNotifyFn, netvista.fwps_vswitch_runtime_state_save_callback0, vSwitchRuntimeStateSaveNotifyFn, vSwitchRuntimeStateSaveNotifyFn callback function [Network Drivers Starting with Windows Vista]
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0
 - fwpsk/FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fwpsk.h
api_name:
 - vSwitchRuntimeStateSaveNotifyFn
---

# FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0 callback function


## -description

The filter engine calls the *vSwitchRuntimeStateSaveNotifyFn* (*FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0*) callout function to notify a callout driver about virtual switch  run-time state save events.

> [!NOTE]
> *FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0* is a specific version of *FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK*. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.


## -parameters

### -param notifyContext 

[in, optional]
A pointer to a context provided by the callout driver. The driver passed this pointer to the *notifyContext* parameter of the [FwpsvSwitchEventsSubscribe0](./nf-fwpsk-fwpsvswitcheventssubscribe0.md)
 function. This parameter is optional and can be NULL.

### -param completionContext 

[in]
A pointer to a completion context provided by the callout driver. This parameter is optional and can be NULL.

### -param eventType 

[in]
The type of virtual switch event  specified as one of the [FWPS_VSWITCH_EVENT_TYPE](./ne-fwpsk-fwps_vswitch_event_type_.md) enumeration values. For more information, see Remarks.

### -param vSwitch 

[in]
A pointer to an [NDIS_SWITCH_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_switch_parameters.md) structure that contains information about a virtual switch.


> [!NOTE]
> The information in the [NDIS_SWITCH_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_switch_parameters.md) structure reflects the initial state of the virtual switch, not necessarily its current state. In particular, the **NumSwitchPorts** and **IsActive** members might still have their initial value of zero, unless a virtual switch PnP event has been triggered. Current state information can be found in the other parameters to this callback function.

### -param portId 

[in]
The source switch port identifier.


#### - **runtimeState

The location of the run-time state output result buffer.

### -param runtimeStateLength

[out]
The length, in bytes, of the run-time state information in the run-time state buffer.


#### - runtimeState

The location of the run-time state output result buffer.

## -returns

A callout's *FWPS_VSWITCH_RUNTIME_STATE_SAVE_CALLBACK0* function returns one of the following NTSTATUS codes.

|Return code|Description|
|--- |--- |
|**STATUS_SUCCESS**|The callout driver accepts the notification from the filter engine.|
|**STATUS_PENDING**|The operation is pending and will be completed later.  The callout  driver will  call the [FwpsvSwitchNotifyComplete0](nf-fwpsk-fwpsvswitchnotifycomplete0.md) function to complete the pending operation.|
|**Other status codes**|An error occurred.|

## -remarks

A callout driver registers a *vSwitchRuntimeStateSaveNotifyFn* function  by calling  the [FwpsvSwitchEventsSubscribe0](nf-fwpsk-fwpsvswitcheventssubscribe0.md)
 function.

If the *vSwitchRuntimeStateSaveNotifyFn* callback is registered, the callout will be notified to retrieve a source VM’s run-time state and to restore a target VM’s run-time state during live migration or a local save and restore operation. In the save case, the *eventType* parameter of *vSwitchRuntimeStateSaveNotifyFn* is set to    FWPS_VSWITCH_EVENT_RUNTIME_STATE_SAVE.

The virtual switch extension protocol driver issues an object identifier (OID) method request of [OID_SWITCH_NIC_SAVE](/windows-hardware/drivers/network/oid-switch-nic-save) during an operation to save run-time data for a virtual switch port. The filter driver returns this data so that run-time data for a virtual switch port can be saved and restored at a later time. 

After the run-time data blob from all callouts are collected, WFP fills the [NDIS_SWITCH_NIC_SAVE_STATE](../ntddndis/ns-ntddndis-_ndis_switch_nic_save_state.md) structure with the harvested data and completes the save state request.

A callout can return STATUS_PENDING from *vSwitchRuntimeStateSaveNotifyFn*. In this case, WFP will return STATUS_PENDING in the [FilterOidRequest](../ndis/nc-ndis-filter_oid_request.md) handler and will complete it at a later time. The callout  driver will  call the [FwpsvSwitchNotifyComplete0](./nf-fwpsk-fwpsvswitchnotifycomplete0.md) function to complete the pending operation. 

See the *vSwitchRuntimeStateRestoreNotifyFn* ([FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0](./nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md)) function for information about restoring the run-time state.

## -see-also

[Callout Driver Callout Functions](../_netvista/index.md)



[FWPS_VSWITCH_EVENT_TYPE](ne-fwpsk-fwps_vswitch_event_type_.md)



[FWPS_VSWITCH_RUNTIME_STATE_RESTORE_CALLBACK0](nc-fwpsk-fwps_vswitch_runtime_state_restore_callback0.md)



[FilterOidRequest](../ndis/nc-ndis-filter_oid_request.md)



[FwpsvSwitchEventsSubscribe0](nf-fwpsk-fwpsvswitcheventssubscribe0.md)



[FwpsvSwitchNotifyComplete0](nf-fwpsk-fwpsvswitchnotifycomplete0.md)



[NDIS_SWITCH_NIC_SAVE_STATE](../ntddndis/ns-ntddndis-_ndis_switch_nic_save_state.md)



[NDIS_SWITCH_PARAMETERS](../ntddndis/ns-ntddndis-_ndis_switch_parameters.md)



[OID_SWITCH_NIC_SAVE](/windows-hardware/drivers/network/oid-switch-nic-save)
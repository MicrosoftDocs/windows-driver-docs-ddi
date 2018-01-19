---
UID: NS:wdfdevice._WDF_DEVICE_PNP_NOTIFICATION_DATA
title: _WDF_DEVICE_PNP_NOTIFICATION_DATA
author: windows-driver-content
description: The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.
old-location: wdf\wdf_device_pnp_notification_data.htm
old-project: wdf
ms.assetid: b49431bf-4b44-4d7b-b3a6-c3d7416bcb53
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_DEVICE_PNP_NOTIFICATION_DATA, WDF_DEVICE_PNP_NOTIFICATION_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WDF_DEVICE_PNP_NOTIFICATION_DATA
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: WDF_DEVICE_PNP_NOTIFICATION_DATA
req.product: Windows 10 or later.
---

# _WDF_DEVICE_PNP_NOTIFICATION_DATA structure



## -description
<p class="CCE_Message">[Applies to KMDF only]

The WDF_DEVICE_PNP_NOTIFICATION_DATA structure describes a state change within a device's Plug and Play state machine.



## -syntax

````
typedef struct _WDF_DEVICE_PNP_NOTIFICATION_DATA {
  WDF_STATE_NOTIFICATION_TYPE Type;
  union {
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
      WDF_DEVICE_PNP_STATE NewState;
    } EnterState;
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
    } PostProcessState;
    struct {
      WDF_DEVICE_PNP_STATE CurrentState;
      WDF_DEVICE_PNP_STATE NewState;
    } LeaveState;
  } Data;
} WDF_DEVICE_PNP_NOTIFICATION_DATA;
````


## -struct-fields

### -field Type

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerator that identifies the type of state change that is being reported.


### -field Data


### -field EnterState

<dl>


</dl>

### -field CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.


### -field NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.

</dd>
</dl>

### -field PostProcessState

<dl>


</dl>

### -field CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.

</dd>
</dl>

### -field LeaveState

<dl>


</dl>

### -field CurrentState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's current state.


### -field NewState

If <b>Type</b> is <b>StateNotificationEnterState</b>, this <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_pnp_state.md">WDF_DEVICE_PNP_STATE</a>-typed enumerator identifies the state machine's next state.

</dd>
</dl>
</dd>
</dl>

## -remarks
The WDF_DEVICE_PNP_NOTIFICATION_DATA structure is an input argument to a driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md">EvtDevicePnpStateChange</a> callback function.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback.md">WdfDeviceInitRegisterPnpStateChangeCallback</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_PNP_NOTIFICATION_DATA structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


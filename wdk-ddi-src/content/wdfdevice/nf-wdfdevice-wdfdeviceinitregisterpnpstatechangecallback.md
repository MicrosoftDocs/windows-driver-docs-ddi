---
UID: NF:wdfdevice.WdfDeviceInitRegisterPnpStateChangeCallback
title: WdfDeviceInitRegisterPnpStateChangeCallback function (wdfdevice.h)
description: The WdfDeviceInitRegisterPnpStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.
old-location: wdf\wdfdeviceinitregisterpnpstatechangecallback.htm
tech.root: wdf
ms.assetid: a14b790a-28d7-4fb8-823f-f37f05e7529f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_51127783-092b-409d-85ad-e502760b62e7.xml, WdfDeviceInitRegisterPnpStateChangeCallback, WdfDeviceInitRegisterPnpStateChangeCallback method, kmdf.wdfdeviceinitregisterpnpstatechangecallback, wdf.wdfdeviceinitregisterpnpstatechangecallback, wdfdevice/WdfDeviceInitRegisterPnpStateChangeCallback
f1_keywords:
 - "wdfdevice/WdfDeviceInitRegisterPnpStateChangeCallback"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceInitRegisterPnpStateChangeCallback
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitRegisterPnpStateChangeCallback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's Plug and Play state machine changes state.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param PnpState [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_pnp_state">WDF_DEVICE_PNP_STATE</a> enumerator that identifies the Plug and Play machine state for which the driver is requesting notification.


### -param EvtDevicePnpStateChange [in]

A caller-supplied pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_pnp_state_change_notification">EvtDevicePnpStateChange</a> event callback function.


### -param CallbackTypes [in]

An ORed combination of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_state_notification_type">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## -returns



If the operation succeeds, <b>WdfDeviceInitRegisterPnpStateChangeCallback</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>
 




## -remarks



If your driver calls <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about <b>WdfDeviceInitRegisterPnpStateChangeCallback</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/state-machines-in-the-framework">State Machines in the Framework</a>.


#### Examples

The following code example registers an event callback function that the framework will call when the device's Plug and Play state machine changes state.

```cpp
status = WdfDeviceInitRegisterPnpStateChangeCallback(
                                                     DeviceInit,
                                                     WdfDevStatePnpEjectFailed,
                                                     MyDrvPnPStateChangeCallback,
                                                     StateNotificationAllStates
                                                     );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_pnp_state_change_notification">EvtDevicePnpStateChange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_device_pnp_state">WDF_DEVICE_PNP_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_state_notification_type">WDF_STATE_NOTIFICATION_TYPE</a>
 

 


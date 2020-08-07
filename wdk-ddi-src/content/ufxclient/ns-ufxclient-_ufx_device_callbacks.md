---
UID: NS:ufxclient._UFX_DEVICE_CALLBACKS
title: _UFX_DEVICE_CALLBACKS (ufxclient.h)
description: The UFX_DEVICE_CALLBACKS structure is used to define then event callback functions supported by the client driver.
old-location: buses\ufx_device_callbacks.htm
tech.root: usbref
ms.assetid: 71D83E2C-8557-45FC-9769-DB71F5FF61FF
ms.date: 05/07/2018
keywords: ["UFX_DEVICE_CALLBACKS structure"]
ms.keywords: "*PUFX_DEVICE_CALLBACKS, PUFX_DEVICE_CALLBACKS, PUFX_DEVICE_CALLBACKS structure pointer [Buses], UFX_DEVICE_CALLBACKS, UFX_DEVICE_CALLBACKS structure [Buses], _UFX_DEVICE_CALLBACKS, buses.ufx_device_callbacks, ufxclient/PUFX_DEVICE_CALLBACKS, ufxclient/UFX_DEVICE_CALLBACKS"
f1_keywords:
 - "ufxclient/UFX_DEVICE_CALLBACKS"
 - "UFX_DEVICE_CALLBACKS"
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ufxclient.h
api_name:
- UFX_DEVICE_CALLBACKS
targetos: Windows
req.typenames: UFX_DEVICE_CALLBACKS, *PUFX_DEVICE_CALLBACKS
---

# _UFX_DEVICE_CALLBACKS structure


## -description


The <b>UFX_DEVICE_CALLBACKS</b> structure is used to define then event callback functions supported by the client driver. 


## -struct-fields




### -field Size

The size of the <b>UFX_DEVICE_CALLBACKS</b> structure.


### -field EvtDeviceHostConnect

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_host_connect">EVT_UFX_DEVICE_HOST_CONNECT</a> callback routine.


### -field EvtDeviceHostDisconnect

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_host_disconnect">EVT_UFX_DEVICE_HOST_DISCONNECT</a> callback routine.


### -field EvtDeviceAddressed

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_addressed">EVT_UFX_DEVICE_ADDRESSED</a> callback routine.


### -field EvtDeviceEndpointAdd

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_endpoint_add">EVT_UFX_DEVICE_ENDPOINT_ADD</a> callback routine.


### -field EvtDeviceDefaultEndpointAdd

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_default_endpoint_add">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a> callback routine.


### -field EvtDeviceUsbStateChange

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_usb_state_change">EVT_UFX_DEVICE_USB_STATE_CHANGE</a> callback routine.


### -field EvtDevicePortChange

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_port_change">EVT_UFX_DEVICE_PORT_CHANGE</a> callback routine.


### -field EvtDevicePortDetect

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_port_detect">EVT_UFX_DEVICE_PORT_DETECT</a> callback routine.


### -field EvtDeviceRemoteWakeupSignal

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_remote_wakeup_signal">EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</a> callback routine.  


### -field EvtDeviceControllerReset

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_controller_reset">EVT_UFX_DEVICE_CONTROLLER_RESET</a> callback routine.


### -field EvtDeviceTestModeSet

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_test_mode_set">EVT_UFX_DEVICE_TEST_MODE_SET</a> callback routine.


### -field EvtDeviceTestHook

Reserved.  Should be set to NULL.


### -field EvtDeviceSuperSpeedPowerFeature

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_super_speed_power_feature">EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</a> callback routine.


### -field EvtDeviceProprietaryChargerDetect

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_detect">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback routine.


### -field EvtDeviceProprietaryChargerSetProperty

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_set_property">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</a> callback routine.


### -field EvtDeviceProprietaryChargerReset

A pointer to the client driver’s <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_reset">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</a> callback routine.


## -remarks



The client driver shall use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufx_device_callbacks_init">UFX_DEVICE_CALLBACKS_INIT</a> macro to initialize the <b>UFX_DEVICE_CALLBACKS</b> structure, and then shall set fields of structure to the appropriate event callback routines prior to calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a> export function.




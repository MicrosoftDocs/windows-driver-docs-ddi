---
UID: NS:ufxclient._UFX_DEVICE_CALLBACKS
title: "_UFX_DEVICE_CALLBACKS"
author: windows-driver-content
description: The UFX_DEVICE_CALLBACKS structure is used to define then event callback functions supported by the client driver.
old-location: buses\ufx_device_callbacks.htm
old-project: usbref
ms.assetid: 71D83E2C-8557-45FC-9769-DB71F5FF61FF
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: PUFX_DEVICE_CALLBACKS, ufxclient/PUFX_DEVICE_CALLBACKS, ufxclient/UFX_DEVICE_CALLBACKS, PUFX_DEVICE_CALLBACKS structure pointer [Buses], *PUFX_DEVICE_CALLBACKS, _UFX_DEVICE_CALLBACKS, buses.ufx_device_callbacks, UFX_DEVICE_CALLBACKS, UFX_DEVICE_CALLBACKS structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ufxclient.h
apiname:
-	UFX_DEVICE_CALLBACKS
product: Windows
targetos: Windows
req.typenames: UFX_DEVICE_CALLBACKS, *PUFX_DEVICE_CALLBACKS
req.product: Windows 10 or later.
---

# _UFX_DEVICE_CALLBACKS structure


## -description


The <b>UFX_DEVICE_CALLBACKS</b> structure is used to define then event callback functions supported by the client driver. 


## -syntax


````
typedef struct _UFX_DEVICE_CALLBACKS {
  ULONG                                           Size;
  PFN_UFX_DEVICE_HOST_CONNECT                     EvtDeviceHostConnect;
  PFN_UFX_DEVICE_HOST_DISCONNECT                  EvtDeviceHostDisconnect;
   PFN_UFX_DEVICE_ADDRESSED                       EvtDeviceAddressed;
  PFN_UFX_DEVICE_ENDPOINT_ADD                     EvtDeviceEndpointAdd;
  PFN_UFX_DEVICE_DEFAULT_ENDPOINT_ADD             EvtDeviceDefaultEndpointAdd;
  PFN_UFX_DEVICE_USB_STATE_CHANGE                 EvtDeviceUsbStateChange;
  PFN_UFX_DEVICE_PORT_CHANGE                      EvtDevicePortChange;
  PFN_UFX_DEVICE_PORT_DETECT                      EvtDevicePortDetect;
  PFN_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL             EvtDeviceRemoteWakeupSignal;
  PFN_UFX_DEVICE_CONTROLLER_RESET                 EvtDeviceControllerReset;
   PFN_UFX_DEVICE_TEST_MODE_SET                   EvtDeviceTestModeSet;
  PFN_UFX_DEVICE_TESTHOOK                         EvtDeviceTestHook;
  PFN_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE        EvtDeviceSuperSpeedPowerFeature;
  PFN_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT       EvtDeviceProprietaryChargerDetect;
  PFN_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY EvtDeviceProprietaryChargerSetProperty;
  PFN_UFX_DEVICE_PROPRIETARY_CHARGER_RESET        EvtDeviceProprietaryChargerReset;
} UFX_DEVICE_CALLBACKS, *PUFX_DEVICE_CALLBACKS;
````


## -struct-fields




### -field Size

The size of the <b>UFX_DEVICE_CALLBACKS</b> structure.


### -field EvtDeviceHostConnect

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_host_connect.md">EVT_UFX_DEVICE_HOST_CONNECT</a> callback routine.


### -field EvtDeviceHostDisconnect

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_host_disconnect.md">EVT_UFX_DEVICE_HOST_DISCONNECT</a> callback routine.


### -field EvtDeviceAddressed

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_addressed.md">EVT_UFX_DEVICE_ADDRESSED</a> callback routine.


### -field EvtDeviceEndpointAdd

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_endpoint_add.md">EVT_UFX_DEVICE_ENDPOINT_ADD</a> callback routine.


### -field EvtDeviceDefaultEndpointAdd

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a> callback routine.


### -field EvtDeviceUsbStateChange

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_usb_state_change.md">EVT_UFX_DEVICE_USB_STATE_CHANGE</a> callback routine.


### -field EvtDevicePortChange

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_port_change.md">EVT_UFX_DEVICE_PORT_CHANGE</a> callback routine.


### -field EvtDevicePortDetect

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_port_detect.md">EVT_UFX_DEVICE_PORT_DETECT</a> callback routine.


### -field EvtDeviceRemoteWakeupSignal

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_remote_wakeup_signal.md">EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</a> callback routine.  


### -field EvtDeviceControllerReset

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_controller_reset.md">EVT_UFX_DEVICE_CONTROLLER_RESET</a> callback routine.


### -field EvtDeviceTestModeSet

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_test_mode_set.md">EVT_UFX_DEVICE_TEST_MODE_SET</a> callback routine.


### -field EvtDeviceTestHook

Reserved.  Should be set to NULL.


### -field EvtDeviceSuperSpeedPowerFeature

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_super_speed_power_feature.md">EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</a> callback routine.


### -field EvtDeviceProprietaryChargerDetect

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md">EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER</a> callback routine.


### -field EvtDeviceProprietaryChargerSetProperty

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_set_property.md">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</a> callback routine.


### -field EvtDeviceProprietaryChargerReset

A pointer to the client driver’s <a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_reset.md">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</a> callback routine.


## -remarks



The client driver shall use the <a href="..\ufxclient\nf-ufxclient-ufx_device_callbacks_init.md">UFX_DEVICE_CALLBACKS_INIT</a> macro to initialize the <b>UFX_DEVICE_CALLBACKS</b> structure, and then shall set fields of structure to the appropriate event callback routines prior to calling the <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a> export function.




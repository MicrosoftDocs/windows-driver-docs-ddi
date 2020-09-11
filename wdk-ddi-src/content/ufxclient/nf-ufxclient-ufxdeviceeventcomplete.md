---
UID: NF:ufxclient.UfxDeviceEventComplete
title: UfxDeviceEventComplete function (ufxclient.h)
description: Informs UFX that the client driver has completed processing a UFX callback function.
old-location: buses\ufxdeviceeventcomplete.htm
tech.root: usbref
ms.assetid: DAC18721-5747-4D5E-8A25-24B80DE77C99
ms.date: 05/07/2018
keywords: ["UfxDeviceEventComplete function"]
ms.keywords: UfxDeviceEventComplete, UfxDeviceEventComplete method [Buses], buses.ufxdeviceeventcomplete, ufxclient/UfxDeviceEventComplete
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxDeviceEventComplete
 - ufxclient/UfxDeviceEventComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxDeviceEventComplete
---

# UfxDeviceEventComplete function


## -description

Informs UFX that the client driver has completed processing a UFX callback function.

## -parameters

### -param UfxDevice 

[in]
A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

### -param Status 

[in]
Status of the event being completed.

## -remarks

The client driver calls <b>UfxDeviceEventComplete</b> to signal completion of the following callback functions:

<ul>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_host_connect">EVT_UFX_DEVICE_HOST_CONNECT</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_host_disconnect">EVT_UFX_DEVICE_HOST_DISCONNECT</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_set_property">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_reset">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_addressed">EVT_UFX_DEVICE_ADDRESSED</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_default_endpoint_add">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_usb_state_change">EVT_UFX_DEVICE_USB_STATE_CHANGE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_port_change">EVT_UFX_DEVICE_PORT_CHANGE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_remote_wakeup_signal">EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_test_mode_set">EVT_UFX_DEVICE_TEST_MODE_SET</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_super_speed_power_feature">EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</a>
</li>
<li>
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ufxclient/nc-ufxclient-evt_ufx_device_controller_reset">EVT_UFX_DEVICE_CONTROLLER_RESET</a>
</li>
</ul>
For example, your callback function could use the following code:


```
    EventComplete = TRUE;

    ...

    if (EventComplete) {
        UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    }

```



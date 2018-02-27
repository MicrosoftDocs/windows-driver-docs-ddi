---
UID: NF:ufxclient.UfxDeviceEventComplete
title: UfxDeviceEventComplete function
author: windows-driver-content
description: Informs UFX that the client driver has completed processing a UFX callback function.
old-location: buses\ufxdeviceeventcomplete.htm
old-project: usbref
ms.assetid: DAC18721-5747-4D5E-8A25-24B80DE77C99
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UfxDeviceEventComplete, UfxDeviceEventComplete method [Buses], buses.ufxdeviceeventcomplete, ufxclient/UfxDeviceEventComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	ufxclient.h
apiname:
-	UfxDeviceEventComplete
product: Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceEventComplete function


## -description


Informs UFX that the client driver has completed processing a UFX callback function.


## -syntax


````
VOID UfxDeviceEventComplete(
  [in] UFXDEVICE UfxDevice,
  [in] NTSTATUS  Status
);
````


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="..\ufxclient\nf-ufxclient-ufxdevicecreate.md">UfxDeviceCreate</a>.


### -param Status [in]

Status of the event being completed.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceEventComplete</b> to signal completion of the following callback functions:

<ul>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_host_connect.md">EVT_UFX_DEVICE_HOST_CONNECT</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_host_disconnect.md">EVT_UFX_DEVICE_HOST_DISCONNECT</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_set_property.md">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_proprietary_charger_reset.md">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_addressed.md">EVT_UFX_DEVICE_ADDRESSED</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_default_endpoint_add.md">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_usb_state_change.md">EVT_UFX_DEVICE_USB_STATE_CHANGE</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_port_change.md">EVT_UFX_DEVICE_PORT_CHANGE</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_remote_wakeup_signal.md">EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_test_mode_set.md">EVT_UFX_DEVICE_TEST_MODE_SET</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_super_speed_power_feature.md">EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</a>
</li>
<li>
<a href="..\ufxclient\nc-ufxclient-evt_ufx_device_controller_reset.md">EVT_UFX_DEVICE_CONTROLLER_RESET</a>
</li>
</ul>
For example, your callback function could use the following code:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    EventComplete = TRUE;

    ...

    if (EventComplete) {
        UfxDeviceEventComplete(UfxDevice, STATUS_SUCCESS);
    }
</pre>
</td>
</tr>
</table></span></div>



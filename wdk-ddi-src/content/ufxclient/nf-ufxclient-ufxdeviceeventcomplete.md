---
UID: NF:ufxclient.UfxDeviceEventComplete
title: UfxDeviceEventComplete function
author: windows-driver-content
description: Informs UFX that the client driver has completed processing a UFX callback function.
old-location: buses\ufxdeviceeventcomplete.htm
old-project: usbref
ms.assetid: DAC18721-5747-4D5E-8A25-24B80DE77C99
ms.author: windowsdriverdev
ms.date: 3/29/2018
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ufxclient.h
api_name:
-	UfxDeviceEventComplete
product:
- Windows
targetos: Windows
req.typenames: UFX_HARDWARE_FAILURE_CONTEXT, *PUFX_HARDWARE_FAILURE_CONTEXT
req.product: Windows 10 or later.
---

# UfxDeviceEventComplete function


## -description


Informs UFX that the client driver has completed processing a UFX callback function.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


### -param Status [in]

Status of the event being completed.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceEventComplete</b> to signal completion of the following callback functions:

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187852">EVT_UFX_DEVICE_HOST_CONNECT</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187853">EVT_UFX_DEVICE_HOST_DISCONNECT</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187858">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187857">EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187847">EVT_UFX_DEVICE_ADDRESSED</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187849">EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187863">EVT_UFX_DEVICE_USB_STATE_CHANGE</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187854">EVT_UFX_DEVICE_PORT_CHANGE</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187859">EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187862">EVT_UFX_DEVICE_TEST_MODE_SET</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187860">EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt187848">EVT_UFX_DEVICE_CONTROLLER_RESET</a>
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



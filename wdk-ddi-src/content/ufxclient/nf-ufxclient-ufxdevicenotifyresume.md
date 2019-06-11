---
UID: NF:ufxclient.UfxDeviceNotifyResume
title: UfxDeviceNotifyResume function (ufxclient.h)
description: Notifies UFX about a USB bus resume event.
old-location: buses\ufxdevicenotifyresume.htm
tech.root: usbref
ms.assetid: A89E9E65-937D-455F-A718-A6BC7611BB8F
ms.date: 05/07/2018
ms.keywords: UfxDeviceNotifyResume, UfxDeviceNotifyResume method [Buses], buses.ufxdevicenotifyresume, ufxclient/UfxDeviceNotifyResume
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
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- ufxclient.h
api_name:
- UfxDeviceNotifyResume
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceNotifyResume function


## -description


Notifies UFX about a USB bus resume event.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt187951">UfxDeviceCreate</a>.


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceNotifyResume</b> when it receives a bus resume event. The controller should return to the same state it was in at the time of the bus resume event.

The client driver typically calls <b>UfxDeviceNotifyResume</b> from its <a href="https://msdn.microsoft.com/d2d505e0-aeac-4871-8c60-d026b2833043">EvtInterruptDpc</a> callback function.  The following example shows how to handle a resume event.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    case DeviceEventWakeUp:
        if (ControllerContext->Suspended) {
            ControllerContext->Suspended = FALSE;
            UfxDeviceNotifyResume(ControllerContext->UfxDevice);
        }
        break;
</pre>
</td>
</tr>
</table></span></div>



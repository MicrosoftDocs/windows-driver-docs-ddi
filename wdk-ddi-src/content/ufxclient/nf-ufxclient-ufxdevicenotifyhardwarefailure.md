---
UID: NF:ufxclient.UfxDeviceNotifyHardwareFailure
title: UfxDeviceNotifyHardwareFailure function (ufxclient.h)
description: Notifies UFX about a non-recoverable hardware failure in the controller.
old-location: buses\ufxdevicenotifyhardwarefailure.htm
tech.root: usbref
ms.assetid: 2EEA262C-5186-4450-A01D-212278ED710B
ms.date: 05/07/2018
ms.keywords: UfxDeviceNotifyHardwareFailure, UfxDeviceNotifyHardwareFailure method [Buses], buses.ufxdevicenotifyhardwarefailure, ufxclient/UfxDeviceNotifyHardwareFailure
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
- UfxDeviceNotifyHardwareFailure
product:
- Windows
targetos: Windows
req.typenames: 
---

# UfxDeviceNotifyHardwareFailure function


## -description


Notifies UFX about a non-recoverable hardware failure in the controller.


## -parameters




### -param UfxDevice [in]

A handle to a UFX device object that the driver created by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.


### -param HardwareFailureContext [in, optional]

Optional pointer to a client driver-defined <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ufxbase/ns-ufxbase-_ufx_hardware_failure_context">UFX_HARDWARE_FAILURE_CONTEXT</a> structure containing controller-specific information about the hardware failure.  


## -returns



This method does not return a value.




## -remarks



The client driver calls <b>UfxDeviceNotifyHardwareFailure</b> when the controller has entered a non-recoverable hardware failure (such as PHY lockup). UFX can try resetting the controller to see if the controller can be recovered. The following example shows the syntax for the call:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    UfxDeviceNotifyHardwareFailure(
        ControllerContext->UfxDevice,
        (PUFX_HARDWARE_FAILURE_CONTEXT) HardwareFailureContext);

</pre>
</td>
</tr>
</table></span></div>



---
UID: NC:hdaudio.PGET_DEVICE_INFORMATION
title: PGET_DEVICE_INFORMATION (hdaudio.h)
description: The GetDeviceInformation routine retrieves information about the HD Audio controller device.The function pointer type for a GetDeviceInformation routine is defined as follows.
old-location: audio\getdeviceinformation.htm
tech.root: audio
ms.assetid: bdd08133-0641-4eea-bfa3-75f700356132
ms.date: 05/08/2018
keywords: ["PGET_DEVICE_INFORMATION callback function"]
ms.keywords: GetDeviceInformation, GetDeviceInformation callback function [Audio Devices], PGET_DEVICE_INFORMATION, PGET_DEVICE_INFORMATION callback, aud-prop2_9e39061d-0e06-4871-b92c-d4bd7aa98815.xml, audio.getdeviceinformation, hdaudio/GetDeviceInformation
f1_keywords:
 - "hdaudio/GetDeviceInformation"
 - "GetDeviceInformation"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- hdaudio.h
api_name:
- GetDeviceInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# PGET_DEVICE_INFORMATION callback function


## -description


The <code>GetDeviceInformation</code> routine retrieves information about the HD Audio controller device.

The function pointer type for a <code>GetDeviceInformation</code> routine is defined as follows.


## -parameters




### -param _context [in]

Specifies the context value from the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a> or the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a> structure.


### -param DeviceInformation [in, out]

Retrieves information about the HD Audio controller device. This parameter points to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_device_information">HDAUDIO_DEVICE_INFORMATION</a> structure into which the routine writes the device information.


## -returns



<code>GetDeviceInformation</code> returns STATUS_SUCCESS if the call succeeds. Otherwise, the routine returns an appropriate error code. The following table shows a possible return status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the size specified at the beginning of the <i>deviceInformation</i> buffer is too small.

</td>
</tr>
</table>
 




## -remarks



This routine retrieves device-dependent information that is static-that is, the information does not change dynamically over time.

The <i>deviceInformation</i> parameter is a pointer to a buffer that contains an HDAUDIO_DEVICE_INFORMATION structure into which the routine writes information about the HD Audio controller. Before calling <code>GetDeviceInformation</code>, the caller allocates the buffer and writes the buffer's size in bytes into the <b>Size</b> member at the beginning of the buffer.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface">HDAUDIO_BUS_INTERFACE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_bus_interface_v2">HDAUDIO_BUS_INTERFACE_V2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/ns-hdaudio-_hdaudio_device_information">HDAUDIO_DEVICE_INFORMATION</a>
 

 


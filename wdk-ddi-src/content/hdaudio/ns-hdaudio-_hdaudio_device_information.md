---
UID: NS:hdaudio._HDAUDIO_DEVICE_INFORMATION
title: _HDAUDIO_DEVICE_INFORMATION (hdaudio.h)
description: The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.
old-location: audio\hdaudio_device_information.htm
tech.root: audio
ms.assetid: 091aee9d-5ecd-481a-b5e2-28b4828b2c2e
ms.date: 05/08/2018
ms.keywords: "*PHDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION, HDAUDIO_DEVICE_INFORMATION structure [Audio Devices], PHDAUDIO_DEVICE_INFORMATION, PHDAUDIO_DEVICE_INFORMATION structure pointer [Audio Devices], _HDAUDIO_DEVICE_INFORMATION, aud-prop2_3350e3d4-dfbe-4002-b237-2395f4a07c7f.xml, audio.hdaudio_device_information, hdaudio/HDAUDIO_DEVICE_INFORMATION, hdaudio/PHDAUDIO_DEVICE_INFORMATION"
ms.topic: struct
f1_keywords:
 - "hdaudio/HDAUDIO_DEVICE_INFORMATION"
req.header: hdaudio.h
req.include-header: Hdaudio.h
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
- hdaudio.h
api_name:
- HDAUDIO_DEVICE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_DEVICE_INFORMATION, *PHDAUDIO_DEVICE_INFORMATION
---

# _HDAUDIO_DEVICE_INFORMATION structure


## -description


The HDAUDIO_DEVICE_INFORMATION structure specifies the hardware capabilities of the HD Audio bus controller.


## -struct-fields




### -field Size

Specifies the size in bytes of the HDAUDIO_DEVICE_INFORMATION structure.


### -field DeviceVersion

Specifies the HD Audio controller device version.


### -field DriverVersion

Specifies the HD Audio bus driver version.


### -field CodecsDetected

Specifies the number of codecs that the HD Audio controller detects on the HD Audio Link.


### -field IsStripingSupported

Specifies whether the HD Audio controller supports <a href="https://docs.microsoft.com/windows-hardware/drivers/audio/striping">striping</a>. If <b>TRUE</b>, it supports striping (with at least two SDO lines). If <b>FALSE</b>, it does not support striping.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a> routine uses this structure to provide information about the HD Audio controller's device-specific capabilities to clients.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/hdaudio/nc-hdaudio-pget_device_information">GetDeviceInformation</a>
 

 


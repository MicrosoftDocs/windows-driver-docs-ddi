---
UID: NS:hdaudio._HDAUDIO_DEVICE_INFORMATION_V2
title: "_HDAUDIO_DEVICE_INFORMATION_V2"
author: windows-driver-content
description: The HDAUDIO_DEVICE_INFORMATION_V2 structure specifies the hardware capabilities of the HD Audio bus controller.
tech.root: audio
ms.date: 02/01/2019
ms.keywords: "*PHDAUDIO_DEVICE_INFORMATION_V2, HDAUDIO_DEVICE_INFORMATION_V2, HDAUDIO_DEVICE_INFORMATION_V2 structure [Audio Devices], PHDAUDIO_DEVICE_INFORMATION_V2, PHDAUDIO_DEVICE_INFORMATION_V2 structure pointer [Audio Devices], _HDAUDIO_DEVICE_INFORMATION_V2, aud-prop2_3350e3d4-dfbe-4002-b237-2395f4a07c7f.xml, audio.HDAUDIO_DEVICE_INFORMATION_V2, hdaudio/HDAUDIO_DEVICE_INFORMATION_V2, hdaudio/PHDAUDIO_DEVICE_INFORMATION_V2"
ms.topic: struct
f1_keywords:
 - "hdaudio/HDAUDIO_DEVICE_INFORMATION_V2"
req.header: hdaudio.h
req.include-header: Hdaudio.h
req.target-type: Windows
req.target-min-winverclnt: 19H1
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
- HDAUDIO_DEVICE_INFORMATION_V2
product:
- Windows
targetos: Windows
req.typenames: HDAUDIO_DEVICE_INFORMATION_V2, *PHDAUDIO_DEVICE_INFORMATION_V2
ms.custom: 19H1 
---

# _HDAUDIO_DEVICE_INFORMATION_V2 structure


## -description

The _HDAUDIO_DEVICE_INFORMATION_V2 structure specifies the hardware capabilities of the HD Audio bus controller.


## -struct-fields

### -field Size

Specifies the size in bytes of the _HDAUDIO_DEVICE_INFORMATION_V2 structure.

### -field DeviceVersion

Specifies the HD Audio controller device version.


### -field DriverVersion

Specifies the HD Audio bus driver version.


### -field CodecsDetected

Specifies the number of codecs that the HD Audio controller detects on the HD Audio Link.


### -field IsStripingSupported

Specifies whether the HD Audio controller supports [Striping](https://docs.microsoft.com/windows-hardware/drivers/audio/striping). If **TRUE**, it supports striping (with at least two SDO lines). If **FALSE**, it does not support striping.

### -field CtrlRevision

HDA controller revision.

### -field CtrlVendorId 

HDA controller vendor ID.

### -field - CtrlDeviceId

HDA controller device ID.



## -remarks

With the release of Windows 1903 the GetDeviceInformation method of all the HDAUDIO_BUS_INTERFACE* was expanded to also accept a larger input structure: _HDAUDIO_DEVICE_INFORMATION_V2. The original input structure of [HDAUDIO_DEVICE_INFORMATION](ns-hdaudio-_hdaudio_device_information.md) continues to be supported. 

If the hdaudbus supports the new size, it inits all the fields and sets the Size field to sizeof(_HDAUDIO_DEVICE_INFORMATION_V2), else it returns the information only for _HDAUDIO_DEVICE_INFORMATION and sets the Size field to sizeof(_HDAUDIO_DEVICE_INFORMATION).

**Usage Examples**

```cpp
_HDAUDIO_DEVICE_INFORMATION_V2 info;

_HDAUDIO_DEVICE_INFORMATION_V2_INIT(&info);

status = m_BusIntV3->GetDeviceInformation(m_BusIntV3->Context, (PHDAUDIO_DEVICE_INFORMATION)&info);
```    

The [GetDeviceInformation](https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information) routine uses the _HDAUDIO_DEVICE_INFORMATION_V2 structure to provide information about the HD Audio controller's device-specific capabilities to clients.


## -see-also

[HDAUDIO_DEVICE_INFORMATION](ns-hdaudio-_hdaudio_device_information.md) 

[GetDeviceInformation](https://docs.microsoft.com/windows-hardware/drivers/ddi/hdaudio/nc-hdaudio-pget_device_information) 

 

 


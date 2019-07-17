---
UID: NE:portabledevice.tagWPD_DEVICE_TYPES
title: WPD_DEVICE_TYPES (portabledevice.h)
description: The WPD_DEVICE_TYPES enumeration type describes the different Windows Portable Devices (WPD) types used to determine the basic classification and visual appearance of a portable device.
old-location: wpddk\wpd_device_types.htm
tech.root: wpd_dk
ms.assetid: c0f1cd63-38d0-4780-81f0-b0969957018c
ms.date: 02/15/2018
ms.keywords: WPD_DEVICE_TYPES, WPD_DEVICE_TYPES enumeration, WPD_DEVICE_TYPE_CAMERA, WPD_DEVICE_TYPE_GENERIC, WPD_DEVICE_TYPE_MEDIA_PLAYER, WPD_DEVICE_TYPE_PHONE, portabledevice/WPD_DEVICE_TYPES, portabledevice/WPD_DEVICE_TYPE_CAMERA, portabledevice/WPD_DEVICE_TYPE_GENERIC, portabledevice/WPD_DEVICE_TYPE_MEDIA_PLAYER, portabledevice/WPD_DEVICE_TYPE_PHONE, tagWPD_DEVICE_TYPES, wpddk.wpd_device_types
ms.topic: enum
f1_keywords:
 - "portabledevice/WPD_DEVICE_TYPES"
req.header: portabledevice.h
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
- PortableDevice.h
api_name:
- WPD_DEVICE_TYPES
product:
- Windows
targetos: Windows
req.typenames: WPD_DEVICE_TYPES
ms.custom: RS5
---

# tagWPD_DEVICE_TYPES enumeration


## -description



The <b>WPD_DEVICE_TYPES</b> enumeration type describes the different Windows Portable Devices (WPD) types used to determine the basic classification and visual appearance of a portable device.




## -enum-fields




### -field WPD_DEVICE_TYPE_GENERIC

A generic Windows Portable Device. These include multifunction devices that do not fall into one of the other <b>WPD_DEVICE_TYPES</b> enumeration values.


### -field WPD_DEVICE_TYPE_CAMERA

A camera device, such as a digital still camera.


### -field WPD_DEVICE_TYPE_MEDIA_PLAYER

A media player device that may support playing audio, video, or viewing pictures (such as a portable music player or Portable Media Center). Not all of this functionally is required to be classified as a <b>WPD_DEVICE_TYPE_MEDIA_PLAYER</b>. For example, Portable Music Player devices that only support audio output are classified as <b>WPD_DEVICE_TYPE_MEDIA_PLAYER</b>.


### -field WPD_DEVICE_TYPE_PHONE

A phone device, such as a mobile phone.


### -field WPD_DEVICE_TYPE_VIDEO


### -field WPD_DEVICE_TYPE_PERSONAL_INFORMATION_MANAGER


### -field WPD_DEVICE_TYPE_AUDIO_RECORDER




## -remarks



<b>WPD_DEVICE_TYPES</b> are read using the <b>IPortableDeviceManager</b> interface. WPD applications may use these values to determine the generic visual appearance of the device. For example, a camera picture is displayed for camera-like devices, a mobile phone picture is displayed for phone-like devices, and so on.

<div class="alert"><b>Note</b>  WPD applications must use the capabilities of the portable device to determine functionally, not the <b>WPD_DEVICE_TYPE</b> value.</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff597672(v=vs.85)">Structures and Enumeration Types</a>
 

 


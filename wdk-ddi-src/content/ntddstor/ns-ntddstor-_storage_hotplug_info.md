---
UID: NS:ntddstor._STORAGE_HOTPLUG_INFO
title: "_STORAGE_HOTPLUG_INFO"
author: windows-driver-content
description: The STORAGE_HOTPLUG_INFO structure provides hotplug information for a device.
old-location: storage\storage_hotplug_info.htm
tech.root: storage
ms.assetid: dcfd5a42-cb76-4386-9f8f-98e0a217c49a
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_HOTPLUG_INFO, PSTORAGE_HOTPLUG_INFO, PSTORAGE_HOTPLUG_INFO structure pointer [Storage Devices], STORAGE_HOTPLUG_INFO, STORAGE_HOTPLUG_INFO structure [Storage Devices], _STORAGE_HOTPLUG_INFO, ntddstor/PSTORAGE_HOTPLUG_INFO, ntddstor/STORAGE_HOTPLUG_INFO, storage.storage_hotplug_info, structs-general_36f1b63b-a574-47e7-85b0-10954c2d84d9.xml"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	STORAGE_HOTPLUG_INFO
product:
- Windows
targetos: Windows
req.typenames: STORAGE_HOTPLUG_INFO, *PSTORAGE_HOTPLUG_INFO
---

# _STORAGE_HOTPLUG_INFO structure


## -description


The STORAGE_HOTPLUG_INFO structure provides hotplug information for a device. 


## -struct-fields




### -field Size

Indicates the size, in bytes, of this structure.


### -field MediaRemovable

Specifies whether the media is removable. If set to a nonzero value, the device media is removable. If set to zero, the device media is not removable. 


### -field MediaHotplug

Specifies whether the media is lockable. If set to a nonzero value, the device media is not lockable. If set to zero, the device media is lockable.


### -field DeviceHotplug

Specifies whether the device is a hotplug device. If set to a nonzero value, the device is a hotplug device. If set to zero, the device is not a hotplug device.


### -field WriteCacheEnableOverride

Do not use; set the value to <b>NULL</b>.


## -remarks



The value of the <b>Size</b> member also identifies the version of this structure. New members will be added to this structure in the future. If the value of the <b>Size</b> member is <b>sizeof</b>(STORAGE_HOTPLUG_INFO), the current version of the structure is the same as the version you compiled with. If the value is not <b>sizeof</b>(STORAGE_HOTPLUG_INFO), the current version contains additional members.

Microsoft Windows XP includes support for hotplug devices. A hotplug device refers to a device whose <b>RemovalPolicy</b> value displayed in the Device Manager is <b>ExpectSurpriseRemoval</b>. To query whether a particular device is a hotplug device, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560554">IOCTL_STORAGE_GET_HOTPLUG_INFO</a> request. To set the hotplug properties of a device, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560606">IOCTL_STORAGE_SET_HOTPLUG_INFO</a> request.

In the case of the IOCTL_STORAGE_SET_HOTPLUG_INFO request, the <b>DeviceHotplug</b> member of the STORAGE_HOTPLUG_INFO structure determines what action is taken. If the value of that member is nonzero, the value for the device's removal policy in the registry is set to <b>ExpectSurpriseRemoval</b> and all levels of caching are disabled. If the value of <b>DeviceHotplug</b> is zero, the removal policy is set to <b>ExpectOrderlyRemoval</b>, and caching may be selectively enabled. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560554">IOCTL_STORAGE_GET_HOTPLUG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560606">IOCTL_STORAGE_SET_HOTPLUG_INFO</a>
 

 


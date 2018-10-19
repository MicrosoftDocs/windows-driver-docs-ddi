---
UID: NS:ntddstor._STORAGE_DEVICE_NUMBER
title: "_STORAGE_DEVICE_NUMBER"
author: windows-driver-content
description: The STORAGE_DEVICE_NUMBER structure is used in conjunction with the IOCTL_STORAGE_GET_DEVICE_NUMBER request to retrieve the FILE_DEVICE_XXX device type, the device number, and, for a device that can be partitioned, the partition number assigned to a device by the driver when the device is started.
old-location: storage\storage_device_number.htm
tech.root: storage
ms.assetid: 3efed879-bde4-44ea-9af5-fc35a2ac27fc
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_DEVICE_NUMBER, PSTORAGE_DEVICE_NUMBER, PSTORAGE_DEVICE_NUMBER structure pointer [Storage Devices], STORAGE_DEVICE_NUMBER, STORAGE_DEVICE_NUMBER structure [Storage Devices], _STORAGE_DEVICE_NUMBER, ntddstor/PSTORAGE_DEVICE_NUMBER, ntddstor/STORAGE_DEVICE_NUMBER, storage.storage_device_number, structs-general_e5b6df4e-787c-415b-82ed-14dffa34a95e.xml"
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
-	STORAGE_DEVICE_NUMBER
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DEVICE_NUMBER, *PSTORAGE_DEVICE_NUMBER
---

# _STORAGE_DEVICE_NUMBER structure


## -description


The STORAGE_DEVICE_NUMBER structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a> request to retrieve the FILE_DEVICE_<i>XXX</i> device type, the device number, and, for a device that can be partitioned, the partition number assigned to a device by the driver when the device is started. 


## -struct-fields




### -field DeviceType

Specifies one of the system-defined FILE_DEVICE_<i>XXX</i> constants indicating the type of device (such as FILE_DEVICE_DISK, FILE_DEVICE_KEYBOARD, and so forth) or a vendor-defined value for a new type of device. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>. 


### -field DeviceNumber

Indicates the number of this device. This value is set to 0xFFFFFFFF (-1) for the disks that represent the physical paths of an MPIO disk.


### -field PartitionNumber

Indicates the partition number of the device is returned in this member, if the device can be partitioned. Otherwise, -1 is returned. 


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a> request is usually issued by a fault-tolerant disk driver.

The values in the STORAGE_DEVICE_NUMBER structure are guaranteed to remain unchanged until the system is rebooted. They are not guaranteed to be persistent across boots.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560551">IOCTL_STORAGE_GET_DEVICE_NUMBER</a>
 

 


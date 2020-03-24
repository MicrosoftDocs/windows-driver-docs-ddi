---
UID: NS:ntdddisk._DISK_CONTROLLER_NUMBER
title: _DISK_CONTROLLER_NUMBER (ntdddisk.h)
description: DISK_CONTROLLER_NUMBER is used with IOCTL_DISK_CONTROLLER_NUMBER to retrieve the controller number and disk number of an IDE disk.
old-location: storage\disk_controller_number.htm
tech.root: storage
ms.assetid: 5dc9f04b-8d7c-4ac7-9518-8836d56d5eed
ms.date: 03/29/2018
keywords: ["_DISK_CONTROLLER_NUMBER structure"]
ms.keywords: "*PDISK_CONTROLLER_NUMBER, DISK_CONTROLLER_NUMBER, DISK_CONTROLLER_NUMBER structure [Storage Devices], PDISK_CONTROLLER_NUMBER, PDISK_CONTROLLER_NUMBER structure pointer [Storage Devices], _DISK_CONTROLLER_NUMBER, ntdddisk/DISK_CONTROLLER_NUMBER, ntdddisk/PDISK_CONTROLLER_NUMBER, storage.disk_controller_number, structs-disk_5cf21b24-f10f-4484-bb76-22dff0b4e32c.xml"
f1_keywords:
 - "ntdddisk/DISK_CONTROLLER_NUMBER"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h, Ntddk.h, Ntdddisk.h
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
- ntdddisk.h
api_name:
- DISK_CONTROLLER_NUMBER
product:
- Windows
targetos: Windows
req.typenames: DISK_CONTROLLER_NUMBER, *PDISK_CONTROLLER_NUMBER
---

# _DISK_CONTROLLER_NUMBER structure


## -description


DISK_CONTROLLER_NUMBER is used with IOCTL_DISK_CONTROLLER_NUMBER to retrieve the controller number and disk number of an IDE disk. 


## -struct-fields




### -field ControllerNumber

Contains the number of the IDE controller for the disk.


### -field DiskNumber

Contains the number of the disk.


## -remarks



After DISK_CONTROLLER_NUMBER receives the controller number and the disk number, these values can be used to determine whether the disk is attached to the primary or to the secondary IDE controller. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_controller_number">IOCTL_DISK_CONTROLLER_NUMBER</a>
 

 


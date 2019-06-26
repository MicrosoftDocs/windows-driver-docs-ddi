---
UID: NS:ntddcdvd._STORAGE_SET_READ_AHEAD
title: _STORAGE_SET_READ_AHEAD (ntddcdvd.h)
description: The STORAGE_SET_READ_AHEAD structure is used in conjunction with the IOCTL_STORAGE_SET_READ_AHEAD request to instruct the device to skip to the target address upon reaching the trigger address.
old-location: storage\storage_set_read_ahead.htm
tech.root: storage
ms.assetid: 5220230f-5436-4a79-808c-ab840d7009e7
ms.date: 03/29/2018
ms.keywords: "*PSTORAGE_SET_READ_AHEAD, PSTORAGE_SET_READ_AHEAD, PSTORAGE_SET_READ_AHEAD structure pointer [Storage Devices], STORAGE_SET_READ_AHEAD, STORAGE_SET_READ_AHEAD structure [Storage Devices], _STORAGE_SET_READ_AHEAD, ntddcdvd/PSTORAGE_SET_READ_AHEAD, ntddcdvd/STORAGE_SET_READ_AHEAD, storage.storage_set_read_ahead, structs-general_a6938152-7839-43e0-a030-8767d032469c.xml"
ms.topic: struct
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
- ntddcdvd.h
api_name:
- STORAGE_SET_READ_AHEAD
product:
- Windows
targetos: Windows
req.typenames: STORAGE_SET_READ_AHEAD, *PSTORAGE_SET_READ_AHEAD
---

# _STORAGE_SET_READ_AHEAD structure


## -description


The STORAGE_SET_READ_AHEAD structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ni-ntddcdvd-ioctl_storage_set_read_ahead">IOCTL_STORAGE_SET_READ_AHEAD</a> request to instruct the device to skip to the target address upon reaching the trigger address. 


## -struct-fields




### -field TriggerAddress

Indicates the address at which the device jumps to the target address. 


### -field TargetAddress

Indicates the address to jump to. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ni-ntddcdvd-ioctl_storage_set_read_ahead">IOCTL_STORAGE_SET_READ_AHEAD</a>
 

 


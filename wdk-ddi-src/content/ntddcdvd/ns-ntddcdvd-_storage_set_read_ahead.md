---
UID: NS:ntddcdvd._STORAGE_SET_READ_AHEAD
title: "_STORAGE_SET_READ_AHEAD"
author: windows-driver-content
description: The STORAGE_SET_READ_AHEAD structure is used in conjunction with the IOCTL_STORAGE_SET_READ_AHEAD request to instruct the device to skip to the target address upon reaching the trigger address.
old-location: storage\storage_set_read_ahead.htm
old-project: storage
ms.assetid: 5220230f-5436-4a79-808c-ab840d7009e7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSTORAGE_SET_READ_AHEAD, PSTORAGE_SET_READ_AHEAD, PSTORAGE_SET_READ_AHEAD structure pointer [Storage Devices], STORAGE_SET_READ_AHEAD, STORAGE_SET_READ_AHEAD structure [Storage Devices], _STORAGE_SET_READ_AHEAD, ntddcdvd/PSTORAGE_SET_READ_AHEAD, ntddcdvd/STORAGE_SET_READ_AHEAD, storage.storage_set_read_ahead, structs-general_a6938152-7839-43e0-a030-8767d032469c.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddcdvd.h
apiname:
-	STORAGE_SET_READ_AHEAD
product: Windows
targetos: Windows
req.typenames: STORAGE_SET_READ_AHEAD, *PSTORAGE_SET_READ_AHEAD
---

# _STORAGE_SET_READ_AHEAD structure


## -description


The STORAGE_SET_READ_AHEAD structure is used in conjunction with the <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_storage_set_read_ahead.md">IOCTL_STORAGE_SET_READ_AHEAD</a> request to instruct the device to skip to the target address upon reaching the trigger address. 


## -syntax


````
typedef struct _STORAGE_SET_READ_AHEAD {
  LARGE_INTEGER TriggerAddress;
  LARGE_INTEGER TargetAddress;
} STORAGE_SET_READ_AHEAD, *PSTORAGE_SET_READ_AHEAD;
````


## -struct-fields




### -field TriggerAddress

Indicates the address at which the device jumps to the target address. 


### -field TargetAddress

Indicates the address to jump to. 


## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_storage_set_read_ahead.md">IOCTL_STORAGE_SET_READ_AHEAD</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STORAGE_SET_READ_AHEAD structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:ntdddisk._REASSIGN_BLOCKS_EX
title: "_REASSIGN_BLOCKS_EX"
author: windows-driver-content
description: The REASSIGN_BLOCKS_EX structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS_EX request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks_ex.htm
old-project: storage
ms.assetid: D1BE17A0-39F1-496A-AD53-46A3F136D793
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX structure pointer [Storage Devices], REASSIGN_BLOCKS_EX, REASSIGN_BLOCKS_EX structure [Storage Devices], _REASSIGN_BLOCKS_EX, ntdddisk/PREASSIGN_BLOCKS_EX, ntdddisk/REASSIGN_BLOCKS_EX, storage.reassign_blocks_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntdddisk.h
api_name:
-	REASSIGN_BLOCKS_EX
product: Windows
targetos: Windows
req.typenames: REASSIGN_BLOCKS_EX, *PREASSIGN_BLOCKS_EX
---

# _REASSIGN_BLOCKS_EX structure


## -description


The <b>REASSIGN_BLOCKS_EX</b> structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_reassign_blocks_ex.md">IOCTL_DISK_REASSIGN_BLOCKS_EX</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.


## -syntax


````
typedef struct _REASSIGN_BLOCKS_EX {
  USHORT        Reserved;
  USHORT        Count;
  LARGE_INTEGER BlockNumber[1];
} REASSIGN_BLOCKS_EX, *PREASSIGN_BLOCKS_EX;
````


## -struct-fields




### -field Reserved

Reserved for system use.


### -field Count

Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign.


### -field BlockNumber

Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool.


## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_reassign_blocks_ex.md">IOCTL_DISK_REASSIGN_BLOCKS_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20REASSIGN_BLOCKS_EX structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


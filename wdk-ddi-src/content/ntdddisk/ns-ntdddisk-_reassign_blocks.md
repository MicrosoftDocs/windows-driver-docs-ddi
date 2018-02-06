---
UID: NS:ntdddisk._REASSIGN_BLOCKS
title: "_REASSIGN_BLOCKS"
author: windows-driver-content
description: The REASSIGN_BLOCKS structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks.htm
old-project: storage
ms.assetid: b79f15d8-b777-43dc-82b9-fcd1ba19aebd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PREASSIGN_BLOCKS structure pointer [Storage Devices], storage.reassign_blocks, structs-disk_dbe1fcc8-083e-41c4-8620-b216cdbecd34.xml, ntdddisk/REASSIGN_BLOCKS, PREASSIGN_BLOCKS, *PREASSIGN_BLOCKS, ntdddisk/PREASSIGN_BLOCKS, REASSIGN_BLOCKS structure [Storage Devices], REASSIGN_BLOCKS, _REASSIGN_BLOCKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
apiname:
-	REASSIGN_BLOCKS
product: Windows
targetos: Windows
req.typenames: "*PREASSIGN_BLOCKS, REASSIGN_BLOCKS"
---

# _REASSIGN_BLOCKS structure


## -description


The <b>REASSIGN_BLOCKS</b> structure is used in conjunction with the <a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_reassign_blocks.md">IOCTL_DISK_REASSIGN_BLOCKS</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.


## -syntax


````
typedef struct _REASSIGN_BLOCKS {
  USHORT Reserved;
  USHORT Count;
  ULONG  BlockNumber[1];
} REASSIGN_BLOCKS, *PREASSIGN_BLOCKS;
````


## -struct-fields




### -field Reserved

Reserved for system use. 


### -field Count

Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign. 


### -field BlockNumber

Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool. 


## -see-also

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_reassign_blocks.md">IOCTL_DISK_REASSIGN_BLOCKS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20REASSIGN_BLOCKS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


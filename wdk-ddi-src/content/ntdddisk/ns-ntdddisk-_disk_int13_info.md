---
UID: NS:ntdddisk._DISK_INT13_INFO
title: "_DISK_INT13_INFO"
author: windows-driver-content
description: The DISK_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an INT13 format.
old-location: storage\disk_int13_info.htm
old-project: storage
ms.assetid: 8a9c335a-1c5f-4379-83bb-21391ae46a3c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DISK_INT13_INFO, DISK_INT13_INFO structure [Storage Devices], ntdddisk/DISK_INT13_INFO, PDISK_INT13_INFO, PDISK_INT13_INFO structure pointer [Storage Devices], structs-disk_fc6ee399-d876-44e3-955a-3ab95c1b5134.xml, *PDISK_INT13_INFO, _DISK_INT13_INFO, storage.disk_int13_info, ntdddisk/PDISK_INT13_INFO
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
-	DISK_INT13_INFO
product: Windows
targetos: Windows
req.typenames: DISK_INT13_INFO, *PDISK_INT13_INFO
---

# _DISK_INT13_INFO structure


## -description


The DISK_INT13_INFO structure is used by the BIOS to report disk detection data for a partition with an INT13 format.


## -syntax


````
typedef struct _DISK_INT13_INFO {
  USHORT DriveSelect;
  ULONG  MaxCylinders;
  USHORT SectorsPerTrack;
  USHORT MaxHeads;
  USHORT NumberDrives;
} DISK_INT13_INFO, *PDISK_INT13_INFO;
````


## -struct-fields




### -field DriveSelect

Corresponds to the Device/Head register defined in the <i>AT Attachment (ATA)</i> specification. When zero, the fourth bit of this register indicates that drive zero is selected. When 1, it indicates that drive one is selected. The values of bits 0, 1, 2, 3, and 6 depend on the command in the command register. Bits 5 and 7 are no longer used. For more information about the values that the Device/Head register can hold, see the ATA specification.


### -field MaxCylinders

Indicates the maximum number of cylinders on the disk. 


### -field SectorsPerTrack

Indicates the number of sectors per track. 


### -field MaxHeads

Indicates the maximum number of disk heads. 


### -field NumberDrives

Indicates the number of drives. 


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_disk_detection_info.md">DISK_DETECTION_INFO</a>



<a href="..\ntdddisk\ns-ntdddisk-_disk_ex_int13_info.md">DISK_EX_INT13_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DISK_INT13_INFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


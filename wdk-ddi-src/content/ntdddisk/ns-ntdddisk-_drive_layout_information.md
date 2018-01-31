---
UID: NS:ntdddisk._DRIVE_LAYOUT_INFORMATION
title: "_DRIVE_LAYOUT_INFORMATION"
author: windows-driver-content
description: The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers.
old-location: storage\drive_layout_information.htm
old-project: storage
ms.assetid: 980cd307-9048-4054-be8e-967d15862a14
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntdddisk/PDRIVE_LAYOUT_INFORMATION, PDRIVE_LAYOUT_INFORMATION, _DRIVE_LAYOUT_INFORMATION, DRIVE_LAYOUT_INFORMATION, ntdddisk/DRIVE_LAYOUT_INFORMATION, *PDRIVE_LAYOUT_INFORMATION, storage.drive_layout_information, PDRIVE_LAYOUT_INFORMATION structure pointer [Storage Devices], structs-disk_4b519d3d-0729-4390-a2e2-b5eb37738db1.xml, DRIVE_LAYOUT_INFORMATION structure [Storage Devices]
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
-	DRIVE_LAYOUT_INFORMATION
product: Windows
targetos: Windows
req.typenames: "*PDRIVE_LAYOUT_INFORMATION, DRIVE_LAYOUT_INFORMATION"
---

# _DRIVE_LAYOUT_INFORMATION structure


## -description


The DRIVE_LAYOUT_INFORMATION structure is obsolete and is provided only to support existing drivers. New drivers must use <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>. 

The DRIVE_LAYOUT_INFORMATION structure is used to report information about a disk drive and its partitions. It is also used to write new drive layout information to the disk. 


## -syntax


````
typedef struct _DRIVE_LAYOUT_INFORMATION {
  ULONG                 PartitionCount;
  ULONG                 Signature;
  PARTITION_INFORMATION PartitionEntry[1];
} DRIVE_LAYOUT_INFORMATION, *PDRIVE_LAYOUT_INFORMATION;
````


## -struct-fields




#### - PartitionCount

Contains the number of partitions on the drive. 


#### - Signature

Contains the disk signature.


#### - PartitionEntry

Contains a variable-length array of <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a> structures, one for each partition on the drive. 


## -remarks


In Windows 2000 and later operating systems, disk drivers should use structures <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a> and <a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a> along with routines <b>IoReadPartitionTableEx</b> and <a href="..\ntddk\nf-ntddk-iosetpartitioninformationex.md">IoSetPartitionInformationEx</a> to read and alter partition information on the disk. 



## -see-also

<a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>

<a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a>

<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>

<a href="..\ntddk\nf-ntddk-iosetpartitioninformation.md">IoSetPartitionInformation</a>

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_drive_layout.md">IOCTL_DISK_SET_DRIVE_LAYOUT</a>

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_drive_layout.md">IOCTL_DISK_GET_DRIVE_LAYOUT</a>

<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_get_partition_info.md">IOCTL_DISK_GET_PARTITION_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVE_LAYOUT_INFORMATION structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


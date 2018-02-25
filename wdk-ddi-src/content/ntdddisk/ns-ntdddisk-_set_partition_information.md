---
UID: NS:ntdddisk._SET_PARTITION_INFORMATION
title: "_SET_PARTITION_INFORMATION"
author: windows-driver-content
description: SET_PARTITION_INFORMATION is used with IOCTL_DISK_SET_PARTITION_INFO to change the partition type of a specified Master Boot Record (MBR) disk partition.
old-location: storage\set_partition_information.htm
old-project: storage
ms.assetid: 882aedda-5ed5-43e0-a370-59a7c7e4c802
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PSET_PARTITION_INFORMATION, ,, A, B, E, F, I, M, N, O, P, PSET_PARTITION_INFORMATION, PSET_PARTITION_INFORMATION structure pointer [Storage Devices], R, S, SET_PARTITION_INFORMATION, SET_PARTITION_INFORMATION structure [Storage Devices], SET_PARTITION_INFORMATION_MBR, T, _, _SET_PARTITION_INFORMATION, ntdddisk/PSET_PARTITION_INFORMATION, ntdddisk/SET_PARTITION_INFORMATION, storage.set_partition_information, structs-disk_b8b3121b-0001-4c1d-ac4d-1eeb1ce79dd3.xml"
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
-	SET_PARTITION_INFORMATION
product: Windows
targetos: Windows
req.typenames: SET_PARTITION_INFORMATION, *PSET_PARTITION_INFORMATION
---

# _SET_PARTITION_INFORMATION structure


## -description


SET_PARTITION_INFORMATION is used with IOCTL_DISK_SET_PARTITION_INFO to change the partition type of a specified Master Boot Record (MBR) disk partition.


## -syntax


````
typedef struct _SET_PARTITION_INFORMATION {
  UCHAR PartitionType;
} SET_PARTITION_INFORMATION, *PSET_PARTITION_INFORMATION;
````


## -struct-fields




### -field PartitionType

Indicates the partition type. IOCTL_DISK_SET_PARTITION_INFO uses this value to set the partition type. See <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a> for a list of system-defined GPT partition types.


## -remarks



The single byte unsigned value, <i>PartitionType</i>, contained in this structure defines a traditional AT Master Boot Record style of partition and cannot be used to define an Extensible Firmware Interface partition (also known as a GUID Partition Table partition). GPT partitions use a GUID to indicate the partition type.




## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_set_partition_information_ex.md">SET_PARTITION_INFORMATION_EX</a>



<a href="..\ntdddisk\ni-ntdddisk-ioctl_disk_set_partition_info.md">IOCTL_DISK_SET_PARTITION_INFO</a>



<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566198">SET_PARTITION_INFORMATION_MBR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566196">SET_PARTITION_INFORMATION_GPT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SET_PARTITION_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


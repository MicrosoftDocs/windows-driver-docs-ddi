---
UID: NS:ntdddisk._PARTITION_INFORMATION_MBR
title: "_PARTITION_INFORMATION_MBR"
author: windows-driver-content
description: PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.
old-location: storage\partition_information_mbr.htm
old-project: storage
ms.assetid: 846f3a1c-ee0a-42d2-bdf1-7bf09406c955
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PPARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR, PARTITION_INFORMATION_MBR structure [Storage Devices], PPARTITION_INFORMATION_MBR, PPARTITION_INFORMATION_MBR structure pointer [Storage Devices], _PARTITION_INFORMATION_MBR, ntdddisk/PARTITION_INFORMATION_MBR, ntdddisk/PPARTITION_INFORMATION_MBR, storage.partition_information_mbr, structs-disk_c386ea16-c8d7-4a5e-8e61-d8e8ddead136.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h, Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	PARTITION_INFORMATION_MBR
product: Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR
---

# _PARTITION_INFORMATION_MBR structure


## -description


PARTITION_INFORMATION_MBR contains information for a Master Boot Record partition that is not held in common with a GUID Partition Table partition.


## -syntax


````
typedef struct _PARTITION_INFORMATION_MBR {
  UCHAR   PartitionType;
  BOOLEAN BootIndicator;
  BOOLEAN RecognizedPartition;
  ULONG   HiddenSectors;
} PARTITION_INFORMATION_MBR, *PPARTITION_INFORMATION_MBR;
````


## -struct-fields




### -field PartitionType

Specifies the partition type. See <a href="..\ntdddisk\ns-ntdddisk-_partition_information.md">PARTITION_INFORMATION</a> for a list of system-defined partition types.


### -field BootIndicator

Indicates, when <b>TRUE</b>, that the partition is bootable. When <b>FALSE</b>, the partition is not bootable.


### -field RecognizedPartition

Indicates, when <b>TRUE</b>, that this is a partition with a recognized partition type. When <b>FALSE</b> this is a not a partition with a recognized partition.


### -field HiddenSectors

Contains the number of hidden sectors in the partition.


### -field PartitionId

 




## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>



<a href="..\ntdddisk\ns-ntdddisk-_partition_information_gpt.md">PARTITION_INFORMATION_GPT</a>



<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PARTITION_INFORMATION_MBR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:ntdddisk._PARTITION_INFORMATION_GPT
title: "_PARTITION_INFORMATION_GPT"
author: windows-driver-content
description: PARTITION_INFORMATION_GPT contains information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition.
old-location: storage\partition_information_gpt.htm
old-project: storage
ms.assetid: f2d76b4c-7acd-4701-b978-3d29dc8cde0b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPARTITION_INFORMATION_GPT, PARTITION_INFORMATION_GPT, PARTITION_INFORMATION_GPT structure [Storage Devices], PPARTITION_INFORMATION_GPT, PPARTITION_INFORMATION_GPT structure pointer [Storage Devices], SET_PARTITION_INFORMATION_GPT, _PARTITION_INFORMATION_GPT, ntdddisk/PARTITION_INFORMATION_GPT, ntdddisk/PPARTITION_INFORMATION_GPT, storage.partition_information_gpt, structs-disk_dad0a2a5-4351-4940-af39-28f7a4005c14.xml"
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
-	PARTITION_INFORMATION_GPT
product: Windows
targetos: Windows
req.typenames: PARTITION_INFORMATION_GPT, *PPARTITION_INFORMATION_GPT
---

# _PARTITION_INFORMATION_GPT structure


## -description


PARTITION_INFORMATION_GPT contains information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition.


## -syntax


````
typedef struct _PARTITION_INFORMATION_GPT {
  GUID    PartitionType;
  GUID    PartitionId;
  ULONG64 Attributes;
  WCHAR   Name[36];
} PARTITION_INFORMATION_GPT, *PPARTITION_INFORMATION_GPT;
````


## -struct-fields




### -field PartitionType

Specifies a GUID that uniquely identifies the partition type. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page. 


### -field PartitionId

Specifies a GUID that uniquely identifies the partition. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page. 


### -field Attributes

Specifies the partition entry attributes used for diagnostics, recovery tools, and other firmware essential to the operation of the device. See Intel's <i>Extensible Firmware Interface</i> specification for further information.


### -field Name

Specifies the partition name in Unicode.


## -see-also

<a href="..\ntdddisk\ns-ntdddisk-_partition_information_ex.md">PARTITION_INFORMATION_EX</a>



<a href="..\ntddk\nf-ntddk-ioreadpartitiontableex.md">IoReadPartitionTableEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20PARTITION_INFORMATION_GPT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


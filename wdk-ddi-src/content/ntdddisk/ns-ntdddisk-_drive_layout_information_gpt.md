---
UID: NS:ntdddisk._DRIVE_LAYOUT_INFORMATION_GPT
title: "_DRIVE_LAYOUT_INFORMATION_GPT"
author: windows-driver-content
description: The DRIVE_LAYOUT_INFORMATION_GPT structure reports the drive signature for a GUID Partition Table partition.
old-location: storage\drive_layout_information_gpt.htm
old-project: storage
ms.assetid: d99180e0-d989-470c-b330-23372938ab25
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PDRIVE_LAYOUT_INFORMATION_GPT, DRIVE_LAYOUT_INFORMATION_GPT, DRIVE_LAYOUT_INFORMATION_GPT structure [Storage Devices], PDRIVE_LAYOUT_INFORMATION_GPT, PDRIVE_LAYOUT_INFORMATION_GPT structure pointer [Storage Devices], _DRIVE_LAYOUT_INFORMATION_GPT, ntdddisk/DRIVE_LAYOUT_INFORMATION_GPT, ntdddisk/PDRIVE_LAYOUT_INFORMATION_GPT, storage.drive_layout_information_gpt, structs-disk_eca2e047-5de8-4960-9066-28eb0dfedb95.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntddk.h
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
-	DRIVE_LAYOUT_INFORMATION_GPT
product: Windows
targetos: Windows
req.typenames: DRIVE_LAYOUT_INFORMATION_GPT, *PDRIVE_LAYOUT_INFORMATION_GPT
---

# _DRIVE_LAYOUT_INFORMATION_GPT structure


## -description


The DRIVE_LAYOUT_INFORMATION_GPT structure reports the drive signature for a GUID Partition Table partition. 


## -syntax


````
typedef struct _DRIVE_LAYOUT_INFORMATION_GPT {
  GUID          DiskId;
  LARGE_INTEGER StartingUsableOffset;
  LARGE_INTEGER UsableLength;
  ULONG         MaxPartitionCount;
} DRIVE_LAYOUT_INFORMATION_GPT, *PDRIVE_LAYOUT_INFORMATION_GPT;
````


## -struct-fields




### -field DiskId

Contains a GUID that uniquely identifies the drive. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page. 


### -field StartingUsableOffset

Contains an offset in bytes to the location immediately following the primary partition table. This offset begins the region on the drive where partitions reside, but partition one is not necessarily located precisely at this offset.


### -field UsableLength

Indicates the total usable space in bytes available on the drive.


### -field MaxPartitionCount

Indicates the maximum number of partitions allowed on the drive.


## -remarks



This structure contains the drive layout information that is specific to a drive with a GUID Partition Table partition. It is encapsulated within the <a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a> structure. For further information see Intel's <i>Extensible Firmware Interface</i> specification.




## -see-also

<a href="..\ntddk\nf-ntddk-ioreadpartitiontable.md">IoReadPartitionTable</a>



<a href="..\ntdddisk\ns-ntdddisk-_drive_layout_information_ex.md">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="..\ntddk\nf-ntddk-iowritepartitiontable.md">IoWritePartitionTable</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20DRIVE_LAYOUT_INFORMATION_GPT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


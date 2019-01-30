---
UID: NS:ntddk._DISK_SIGNATURE
title: "_DISK_SIGNATURE" (ntddk.h)
description: DISK_SIGNATURE contains the disk signature information for a disk's partition table.
old-location: storage\disk_signature.htm
tech.root: storage
ms.assetid: f3fdb436-53b6-4fb3-8746-1f852f7d928a
ms.date: 03/29/2018
ms.keywords: "*PDISK_SIGNATURE, DISK_SIGNATURE, DISK_SIGNATURE structure [Storage Devices], PDISK_SIGNATURE, PDISK_SIGNATURE structure pointer [Storage Devices], _DISK_SIGNATURE, ntddk/DISK_SIGNATURE, ntddk/PDISK_SIGNATURE, storage.disk_signature, structs-disk_6ea56db7-c886-43f2-b9ed-24b0f7e1cb6e.xml"
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: This structure is only available on Windows XP and later.
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
-	ntddk.h
api_name:
-	DISK_SIGNATURE
product:
- Windows
targetos: Windows
req.typenames: DISK_SIGNATURE, *PDISK_SIGNATURE
---

# _DISK_SIGNATURE structure


## -description


DISK_SIGNATURE contains the disk signature information for a disk's partition table.


## -struct-fields




### -field PartitionStyle

Specifies the type of partition.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff563773">PARTITION_STYLE</a> for a description of the possible values.


### -field Mbr


### -field Mbr.Signature

Specifies the signature value, which uniquely identifies the disk. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR. 


### -field Mbr.CheckSum

Specifies the checksum for the master boot record. The <b>Mbr</b> member of the union is used to specify the disk signature data for a disk formatted with a Master Boot Record (MBR) format partition table. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_MBR. 


### -field Gpt


### -field Gpt.DiskId

Specifies the GUID that uniquely identifies the disk. The <b>Gpt</b> member of the union is used to specify the disk signature data for a disk that is formatted with a GUID Partition Table (GPT) format partition table. The GUID data type is described on the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565392">Using GUIDs in Drivers</a> reference page. This member is valid when <b>PartitionStyle</b> is PARTITION_STYLE_GPT. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561447">IoReadDiskSignature</a>
 

 


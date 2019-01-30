---
UID: NS:ntddtape._TAPE_CREATE_PARTITION
title: "_TAPE_CREATE_PARTITION" (ntddtape.h)
description: The TAPE_CREATE_PARTITION structure is used in conjunction with the IOCTL_TAPE_CREATE_PARTITION request to create a specified number of fixed, select, or initiator partitions of a given size on the tape media.
old-location: storage\tape_create_partition.htm
tech.root: storage
ms.assetid: 5020d2c6-f435-4d22-98a3-23318ffc0baf
ms.date: 03/29/2018
ms.keywords: "*PTAPE_CREATE_PARTITION, PTAPE_CREATE_PARTITION, PTAPE_CREATE_PARTITION structure pointer [Storage Devices], TAPE_CREATE_PARTITION, TAPE_CREATE_PARTITION structure [Storage Devices], _TAPE_CREATE_PARTITION, ntddtape/PTAPE_CREATE_PARTITION, ntddtape/TAPE_CREATE_PARTITION, storage.tape_create_partition, structs-tape_3d86a9f7-45b2-48e8-ae21-2ad87641bcf9.xml"
ms.topic: struct
req.header: ntddtape.h
req.include-header: Ntddtape.h, Minitape.h
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
-	ntddtape.h
api_name:
-	TAPE_CREATE_PARTITION
product:
- Windows
targetos: Windows
req.typenames: TAPE_CREATE_PARTITION, *PTAPE_CREATE_PARTITION
---

# _TAPE_CREATE_PARTITION structure


## -description


The TAPE_CREATE_PARTITION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560612">IOCTL_TAPE_CREATE_PARTITION</a> request to create a specified number of fixed, select, or initiator partitions of a given size on the tape media.


## -struct-fields




### -field Method

Indicates the method used to create the partitions. This member can have one of the following values: 

<table>
<tr>
<th>Method</th>
<th>Meaning</th>
</tr>
<tr>
<td>
TAPE_FIXED_PARTITIONS

</td>
<td>
Partitions the tape based on the device's default definition of partitions. The <b>Count</b> and <b>Size</b> parameters are ignored. 

</td>
</tr>
<tr>
<td>
TAPE_SELECT_PARTITIONS

</td>
<td>
Partitions the tape into the number of partitions specified by <b>Count</b>. The <b>Size</b> parameter is ignored. The size of the partitions is determined by the device's default partition size. For more specific information, refer to the documentation for your tape device.

</td>
</tr>
<tr>
<td>
TAPE_INITIATOR_PARTITIONS

</td>
<td>
Partitions the tape into the number and size of partitions specified by <b>Count</b> and <b>Size</b>, respectively, except for the last partition. The size of the last partition is the remainder of the tape. 

</td>
</tr>
</table>
 


### -field Count

Indicates the number of partitions to create.


### -field Size

Indicates the size of each partition, in bytes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560612">IOCTL_TAPE_CREATE_PARTITION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567932">TapeMiniCreatePartition</a>
 

 


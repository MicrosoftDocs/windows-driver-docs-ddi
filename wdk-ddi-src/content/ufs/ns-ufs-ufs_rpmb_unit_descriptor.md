---
UID: NS:ufs.__unnamed_struct_5
title: UFS_RPMB_UNIT_DESCRIPTOR (ufs.h)
description: The UFS_RPMB_UNIT_DESCRIPTOR structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.
old-location: storage\ufs_rpmb_unit_descriptor.htm
tech.root: storage
ms.assetid: 19A066BD-1099-475C-BF81-F1BE7C7778E5
ms.date: 03/29/2018
keywords: ["UFS_RPMB_UNIT_DESCRIPTOR structure"]
ms.keywords: "*PUFS_RPMB_UNIT_DESCRIPTOR, PUFS_RPMB_UNIT_DESCRIPTOR, PUFS_RPMB_UNIT_DESCRIPTOR structure pointer [Storage Devices], UFS_RPMB_UNIT_DESCRIPTOR, UFS_RPMB_UNIT_DESCRIPTOR structure [Storage Devices], storage.ufs_rpmb_unit_descriptor, ufs/PUFS_RPMB_UNIT_DESCRIPTOR, ufs/UFS_RPMB_UNIT_DESCRIPTOR"
f1_keywords:
 - "ufs/UFS_RPMB_UNIT_DESCRIPTOR"
 - "UFS_RPMB_UNIT_DESCRIPTOR"
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ufs.h
api_name:
- UFS_RPMB_UNIT_DESCRIPTOR
targetos: Windows
req.typenames: UFS_RPMB_UNIT_DESCRIPTOR, *PUFS_RPMB_UNIT_DESCRIPTOR
---

# UFS_RPMB_UNIT_DESCRIPTOR structure


## -description


The <b>UFS_RPMB_UNIT_DESCRIPTOR</b> structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_UNIT_IDN</b>.


### -field bUnitIndex

Specifies unit index


### -field bLUEnable

Specifies if the logic unit number (LUN) is enabled. If <b>bLUEnable</b> is equal to 0x00, the logical unit is disabled.


### -field bBootLunID

 


### -field bLUWriteProtect

Specifies if the logical unit is write-protected. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>The logical unit is not write protected.</td>
</tr>
<tr>
<td>0x01</td>
<td>The logical unit is write protected.</td>
</tr>
<tr>
<td>0x02 </td>
<td>The logical unit is permanently write protected.</td>
</tr>
</table>
 


### -field bLUQueueDepth

Specifies the logical unit queue depth. Can be any value from 0x00 to 0xff.


### -field bPSASensitive

Specifies if the logical unit is sensitive to soldering. Contains one of the following values:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>The logical unit is not sensitive to soldering.</td>
</tr>
<tr>
<td>0x01</td>
<td>The logical unit is sensitive to soldering.</td>
</tr>
</table>
 


### -field bMemoryType

Specifies the desired memory type. Equal to 0x0F.


### -field Reserved

Reserved for future use.

Reserved for future use.


### -field bLogicalBlockSize

Specifies the logical block size of the descriptor.


### -field qLogicalBlockCount

Specifies the total number of addressable logical blocks in the logical unit.


### -field dEraseBlockSize

Specifies the erase block size.


### -field bProvisioningType

Specifies the provisioning type.


### -field qPhyMemResourceCount

Specifies the total physical memory resources available in the logical unit.


### -field Reserved2

 




#### - bBootLUNID

Specifies the boot LUN id.


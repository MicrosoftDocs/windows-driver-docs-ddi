---
UID: NS:ufs.UFS_RPMB_UNIT_DESCRIPTOR
title: UFS_RPMB_UNIT_DESCRIPTOR
author: windows-driver-content
description: The UFS_RPMB_UNIT_DESCRIPTOR structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.
old-location: storage\ufs_rpmb_unit_descriptor.htm
old-project: storage
ms.assetid: 19A066BD-1099-475C-BF81-F1BE7C7778E5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ufs_rpmb_unit_descriptor, UFS_RPMB_UNIT_DESCRIPTOR structure [Storage Devices], PUFS_RPMB_UNIT_DESCRIPTOR, *PUFS_RPMB_UNIT_DESCRIPTOR, PUFS_RPMB_UNIT_DESCRIPTOR structure pointer [Storage Devices], UFS_RPMB_UNIT_DESCRIPTOR, ufs/UFS_RPMB_UNIT_DESCRIPTOR, ufs/PUFS_RPMB_UNIT_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ufs.h
apiname:
-	UFS_RPMB_UNIT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_RPMB_UNIT_DESCRIPTOR, *PUFS_RPMB_UNIT_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_RPMB_UNIT_DESCRIPTOR structure


## -description


The <b>UFS_RPMB_UNIT_DESCRIPTOR</b> structure describes the contents of a Replay Protected Memory Block (RBMB) Unit.


## -syntax


````
typedef struct _UFS_RPMB_UNIT_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bUnitIndex;
  UCHAR bLUEnable;
  UCHAR bBootLUNID;
  UCHAR bLUWriteProtect;
  UCHAR bLUQueueDepth;
  UCHAR bPSASensitive;
  UCHAR bMemoryType;
  UCHAR Reserved;
  UCHAR  bLogicalBlockSize;
  UCHAR qLogicalBlockCount[8];
  UCHAR dEraseBlockSize[4];
  UCHAR bProvisioningType;
  UCHAR qPhyMemResourceCount[8];
  UCHAR Reserved[3];
} UFS_RPMB_UNIT_DESCRIPTOR, *PUFS_RPMB_UNIT_DESCRIPTOR;
````


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


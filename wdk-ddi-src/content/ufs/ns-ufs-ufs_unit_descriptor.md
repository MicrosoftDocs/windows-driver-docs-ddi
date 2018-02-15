---
UID: NS:ufs.UFS_UNIT_DESCRIPTOR
title: UFS_UNIT_DESCRIPTOR
author: windows-driver-content
description: The UFS_UNIT_DESCRIPTOR structure describes a generic unit descriptor.
old-location: storage\ufs_unit_descriptor.htm
old-project: storage
ms.assetid: 5D76C266-875A-40AC-9B26-F17978971783
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PUFS_UNIT_DESCRIPTOR structure pointer [Storage Devices], storage.ufs_unit_descriptor, ufs/UFS_UNIT_DESCRIPTOR, ufs/PUFS_UNIT_DESCRIPTOR, UFS_UNIT_DESCRIPTOR structure [Storage Devices], UFS_UNIT_DESCRIPTOR, PUFS_UNIT_DESCRIPTOR, *PUFS_UNIT_DESCRIPTOR
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
-	UFS_UNIT_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: "*PUFS_UNIT_DESCRIPTOR, UFS_UNIT_DESCRIPTOR"
req.product: Windows 10 or later.
---

# UFS_UNIT_DESCRIPTOR structure


## -description


The <b>UFS_UNIT_DESCRIPTOR</b> structure describes a generic unit descriptor.


## -syntax


````
typedef struct _UFS_UNIT_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bUnitIndex;
  UCHAR bLUEnable;
  UCHAR bBootLUNID;
  UCHAR bLUWriteProtect;
  UCHAR bLUQueueDepth;
  UCHAR bPSASensitive;
  UCHAR bMemoryType;
  UCHAR bDataReliability;
  UCHAR  bLogicalBlockSize;
  UCHAR qLogicalBlockCount[8];
  UCHAR dEraseBlockSize[4];
  UCHAR bProvisioningType;
  UCHAR qPhyMemResourceCount[8];
  UCHAR wContextCapabilities[2];
  UCHAR bLargeUnitGranularity_M1;
} UFS_UNIT_DESCRIPTOR, *PUFS_UNIT_DESCRIPTOR;
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

Specifies the desired memory type. The <b>wSupportedMemoryTypes</b> parameter in the <a href="..\ufs\ns-ufs-ufs_geometry_descriptor.md">UFS_GEOMETRY_DESCRIPTOR</a> indicates which memory types are supported by the device


### -field bDataReliability

Specifies if the device is protected against a power failure during a write operation to the logical unit. 


### -field bLogicalBlockSize

Specifies the logical block size of the descriptor. Set the value of this equal to the corresponding value in <b>dOptimalLogicalBlockSize</b> of <a href="..\ufs\ns-ufs-ufs_geometry_descriptor.md">UFS_GEOMETRY_DESCRIPTOR</a> for the specific logical unit memory type.


### -field qLogicalBlockCount

Specifies the total number of addressable logical blocks in the logical unit.


### -field dEraseBlockSize

Specifies the erase block size.


### -field bProvisioningType

Specifies the provisioning type.


### -field qPhyMemResourceCount

Specifies the total physical memory resources available in the logical unit.


### -field wContextCapabilities

Specifies the number of contexts to be supported in each logical unit.


### -field bLargeUnitGranularity_M1

Specifies the Large Unit granularity, minus one.


#### - bBootLUNID

Specifies the boot LUN id.


## -remarks



<b>bPSASensitive</b> and<b> dEraseBlockSize</b> are updated automatically after device configuration.




## -see-also

<a href="..\ufs\ns-ufs-ufs_geometry_descriptor.md">UFS_GEOMETRY_DESCRIPTOR</a>



<a href="..\ufs\ns-ufs-ufs_rpmb_unit_descriptor.md">UFS_RPMB_UNIT_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_UNIT_DESCRIPTOR structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


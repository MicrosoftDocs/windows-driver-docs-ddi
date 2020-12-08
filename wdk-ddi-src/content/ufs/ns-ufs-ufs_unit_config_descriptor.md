---
UID: NS:ufs.__unnamed_struct_1
title: UFS_UNIT_CONFIG_DESCRIPTOR (ufs.h)
description: The UFS_UNIT_CONFIG_DESCRIPTOR structure describes the user configurable parameters within the UFS_CONFIG_DESCRIPTOR.
old-location: storage\ufs_unit_config_descriptor.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["UFS_UNIT_CONFIG_DESCRIPTOR structure"]
ms.keywords: "*PUFS_UNIT_CONFIG_DESCRIPTOR, PUFS_UNIT_CONFIG_DESCRIPTOR, PUFS_UNIT_CONFIG_DESCRIPTOR structure pointer [Storage Devices], UFS_UNIT_CONFIG_DESCRIPTOR, UFS_UNIT_CONFIG_DESCRIPTOR structure [Storage Devices], storage.ufs_unit_config_descriptor, ufs/PUFS_UNIT_CONFIG_DESCRIPTOR, ufs/UFS_UNIT_CONFIG_DESCRIPTOR"
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
targetos: Windows
req.typenames: UFS_UNIT_CONFIG_DESCRIPTOR, *PUFS_UNIT_CONFIG_DESCRIPTOR
f1_keywords:
 - PUFS_UNIT_CONFIG_DESCRIPTOR
 - ufs/PUFS_UNIT_CONFIG_DESCRIPTOR
 - UFS_UNIT_CONFIG_DESCRIPTOR
 - ufs/UFS_UNIT_CONFIG_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - UFS_UNIT_CONFIG_DESCRIPTOR
---

# UFS_UNIT_CONFIG_DESCRIPTOR structure


## -description

The <b>UFS_UNIT_CONFIG_DESCRIPTOR</b> structure describes the user configurable parameters within the <a href="/windows-hardware/drivers/ddi/ufs/ns-ufs-ufs_config_descriptor">UFS_CONFIG_DESCRIPTOR</a>.

## -struct-fields

### -field bLUEnable

Specifies if the logical unit is enabled.

### -field bBootLunID

Specifies if the logical unit is a bootable logical unit.

### -field bLUWriteProtect

Specifies if the Logical Unit is write protected.

### -field bMemoryType

Specifies the Memory type of the device.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Normal Memory type</td>
</tr>
<tr>
<td>0x01</td>
<td>System code memory type</td>
</tr>
<tr>
<td>0x02</td>
<td>Non-Persistent memory type</td>
</tr>
<tr>
<td>0x03</td>
<td>Enhanced memory type 1</td>
</tr>
<tr>
<td>0x04</td>
<td>Enhanced memory type 2</td>
</tr>
<tr>
<td>0x05</td>
<td>Enhanced memory type 3</td>
</tr>
<tr>
<td>0x06</td>
<td>Enhanced memory type 4</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>

### -field dNumAllocUnits

Specifies the number of allocation units assigned to the logical unit.

### -field bDataReliability

<b>bDataReliability</b> defines the device behavior
when a power failure occurs during a write
operation to the logical unit:

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>The logical unit is not protected. Logical
unit's entire data may be lost as a result
of a power failure during a write
operation</td>
</tr>
<tr>
<td>0x01</td>
<td>The logical unit is protected. Logical unit's
data is protected against power failure.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>

### -field bLogicalBlockSize

Specifies the logical block size.

### -field bProvisioningType

Specifies the provisioning type.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Thin Provisioning is disabled (default)</td>
</tr>
<tr>
<td>0x02</td>
<td>Thin Provisioning is enabled and Thin Provisioning Read Zeros (TPRZ)
= 0</td>
</tr>
<tr>
<td>0x03</td>
<td>Thin Provisioning is enabled and TPRZ
= 1</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>

### -field wContextCapabilities

Specifies the Context Capabilities.

### -field Reserved

Reserved for future use.

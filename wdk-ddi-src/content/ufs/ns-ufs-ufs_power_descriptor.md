---
UID: NS:ufs.__unnamed_struct_6
title: UFS_POWER_DESCRIPTOR (ufs.h)
description: UFS_POWER_DESCRIPTOR contains information about the power capabilities and power states of the device.
old-location: storage\ufs_power_descriptor.htm
tech.root: storage
ms.assetid: FCF9DCD1-2C04-47E3-97C5-7ACC28B28C6C
ms.date: 03/29/2018
ms.keywords: "*PUFS_POWER_DESCRIPTOR, PUFS_POWER_DESCRIPTOR, PUFS_POWER_DESCRIPTOR structure pointer [Storage Devices], UFS_POWER_DESCRIPTOR, UFS_POWER_DESCRIPTOR structure [Storage Devices], storage.ufs_power_descriptor, ufs/PUFS_POWER_DESCRIPTOR, ufs/UFS_POWER_DESCRIPTOR"
f1_keywords:
 - "ufs/UFS_POWER_DESCRIPTOR"
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
- UFS_POWER_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: UFS_POWER_DESCRIPTOR, *PUFS_POWER_DESCRIPTOR
---

# UFS_POWER_DESCRIPTOR structure


## -description


<b>UFS_POWER_DESCRIPTOR </b>contains information about the power capabilities and power states of the device.


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_POWER_IDN</b>.


### -field wActiveICCLevelsVCC

Specifies the maximum VCC current value for
each UFS_bActiveICCLevel, based on the index value.


### -field wActiveICCLevelsVCCQ

Specifies the maximum VCCQ current value for
each UFS_bActiveICCLevel, based on the index value.


### -field wActiveICCLevelsVCCQ2

Specifies the maximum VCCQ current value for
each UFS_bActiveICCLevel, based on the index value.


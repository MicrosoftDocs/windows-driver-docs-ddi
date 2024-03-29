---
UID: NS:ufs.UFS_INTERCONNECT_DESCRIPTOR
title: UFS_INTERCONNECT_DESCRIPTOR (ufs.h)
description: UFS_INTERCONNECT_DESCRIPTOR contains the MIPI M-PHY® specification version number and the MIPI 6338 UniPro℠ specification version number.
old-location: storage\ufs_interconnect_descriptor.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["UFS_INTERCONNECT_DESCRIPTOR structure"]
ms.keywords: "*PUFS_INTERCONNECT_DESCRIPTOR, PUFS_INTERCONNECT_DESCRIPTOR, PUFS_INTERCONNECT_DESCRIPTOR structure pointer [Storage Devices], UFS_INTERCONNECT_DESCRIPTOR, UFS_INTERCONNECT_DESCRIPTOR structure [Storage Devices], storage.ufs_interconnect_descriptor, ufs/PUFS_INTERCONNECT_DESCRIPTOR, ufs/UFS_INTERCONNECT_DESCRIPTOR"
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
req.typenames: UFS_INTERCONNECT_DESCRIPTOR, *PUFS_INTERCONNECT_DESCRIPTOR
f1_keywords:
 - PUFS_INTERCONNECT_DESCRIPTOR
 - ufs/PUFS_INTERCONNECT_DESCRIPTOR
 - UFS_INTERCONNECT_DESCRIPTOR
 - ufs/UFS_INTERCONNECT_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ufs.h
api_name:
 - PUFS_INTERCONNECT_DESCRIPTOR
 - UFS_INTERCONNECT_DESCRIPTOR
---

# UFS_INTERCONNECT_DESCRIPTOR structure


## -description

<b>UFS_INTERCONNECT_DESCRIPTOR</b> contains the MIPI M-PHY® specification version number and the MIPI
6338 UniPro℠ specification version number.

## -struct-fields

### -field bLength

Specifies the length, in bytes, of this descriptor.

### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_INTERCONNECT_IDN</b>.

### -field bcdUniproVersion

Specifies the MIPI UniPro℠ version number in Binary Coded Decimal (BCD) format.

### -field bcdMphyVersion

Specifies the MIPI M-PHY® version number in BCD format.


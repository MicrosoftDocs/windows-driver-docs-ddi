---
UID: NS:ufs._UFS_STRING_DESCRIPTOR
title: "_UFS_STRING_DESCRIPTOR"
author: windows-driver-content
description: The UFS_STRING_DESCRIPTOR structure describes either the Manufacturer Name, Product Name, OEM ID, or Serial Number as a string.
old-location: storage\ufs_string_descriptor.htm
old-project: storage
ms.assetid: 1F32DA95-6801-4C48-B3C4-A47C3E1C678B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUFS_STRING_DESCRIPTOR, PUFS_STRING_DESCRIPTOR, PUFS_STRING_DESCRIPTOR structure pointer [Storage Devices], UFS_STRING_DESCRIPTOR, UFS_STRING_DESCRIPTOR structure [Storage Devices], _UFS_STRING_DESCRIPTOR, storage.ufs_string_descriptor, ufs/PUFS_STRING_DESCRIPTOR, ufs/UFS_STRING_DESCRIPTOR"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ufs.h
api_name:
-	UFS_STRING_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_STRING_DESCRIPTOR, *PUFS_STRING_DESCRIPTOR
req.product: Windows 10 or later.
---

# _UFS_STRING_DESCRIPTOR structure


## -description


The <b>UFS_STRING_DESCRIPTOR</b> structure describes either the Manufacturer Name, Product Name, OEM ID, or Serial Number as a string. 


## -struct-fields




### -field bLength

Specifies the length, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_STRING_IDN</b>.


### -field String

Contains either the Manufacturer Name, Product Name, OEM ID, or Serial Number as a string.


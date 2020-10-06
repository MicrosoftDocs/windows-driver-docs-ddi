---
UID: NS:ntdddisk._VERIFY_INFORMATION
title: _VERIFY_INFORMATION (ntdddisk.h)
description: The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.
old-location: storage\verify_information.htm
tech.root: storage
ms.assetid: 7bb5c2ff-9bdb-4958-b290-9edb18d02668
ms.date: 03/29/2018
keywords: ["VERIFY_INFORMATION structure"]
ms.keywords: "*PVERIFY_INFORMATION, PVERIFY_INFORMATION, PVERIFY_INFORMATION structure pointer [Storage Devices], VERIFY_INFORMATION, VERIFY_INFORMATION structure [Storage Devices], _VERIFY_INFORMATION, ntdddisk/PVERIFY_INFORMATION, ntdddisk/VERIFY_INFORMATION, storage.verify_information, structs-disk_fbed0038-effc-40d8-8814-921dfd627a94.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
targetos: Windows
req.typenames: VERIFY_INFORMATION, *PVERIFY_INFORMATION
f1_keywords:
 - _VERIFY_INFORMATION
 - ntdddisk/_VERIFY_INFORMATION
 - PVERIFY_INFORMATION
 - ntdddisk/PVERIFY_INFORMATION
 - VERIFY_INFORMATION
 - ntdddisk/VERIFY_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - VERIFY_INFORMATION
---

# _VERIFY_INFORMATION structure


## -description

The VERIFY_INFORMATION structure provides information used to verify the existence of a disk extent.

## -struct-fields

### -field StartingOffset

Specifies the starting offset, in bytes, of the disk extent.

### -field Length

Indicates the length, in bytes, of the disk extent.

## -remarks

VERIFY_INFORMATION is the output buffer for the <a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_verify">IOCTL_DISK_VERIFY</a> control code.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ni-ntdddisk-ioctl_disk_verify">IOCTL_DISK_VERIFY</a>
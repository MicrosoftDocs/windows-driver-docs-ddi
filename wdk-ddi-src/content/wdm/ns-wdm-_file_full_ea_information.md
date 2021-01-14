---
UID: NS:wdm._FILE_FULL_EA_INFORMATION
title: _FILE_FULL_EA_INFORMATION (wdm.h)
description: The FILE_FULL_EA_INFORMATION structure provides extended attribute (EA) information. This structure is used primarily by network drivers.
old-location: kernel\file_full_ea_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["FILE_FULL_EA_INFORMATION structure"]
ms.keywords: "*PFILE_FULL_EA_INFORMATION, FILE_FULL_EA_INFORMATION, FILE_FULL_EA_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_FULL_EA_INFORMATION, PFILE_FULL_EA_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_FULL_EA_INFORMATION, kernel.file_full_ea_information, kstruct_b_3640566d-def9-44eb-a205-a6361d46e246.xml, wdm/FILE_FULL_EA_INFORMATION, wdm/PFILE_FULL_EA_INFORMATION"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.typenames: FILE_FULL_EA_INFORMATION, *PFILE_FULL_EA_INFORMATION
f1_keywords:
 - _FILE_FULL_EA_INFORMATION
 - wdm/_FILE_FULL_EA_INFORMATION
 - PFILE_FULL_EA_INFORMATION
 - wdm/PFILE_FULL_EA_INFORMATION
 - FILE_FULL_EA_INFORMATION
 - wdm/FILE_FULL_EA_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FILE_FULL_EA_INFORMATION
 - PFILE_FULL_EA_INFORMATION
 - FILE_FULL_EA_INFORMATION
---

# _FILE_FULL_EA_INFORMATION structure


## -description

The <b>FILE_FULL_EA_INFORMATION</b> structure provides extended attribute (EA) information. This structure is used primarily by network drivers.

## -struct-fields

### -field NextEntryOffset

The offset of the next <b>FILE_FULL_EA_INFORMATION</b>-type entry. This member is zero if no other entries follow this one.

### -field Flags

Can be zero or can be set with FILE_NEED_EA, indicating that the file to which the EA belongs cannot be interpreted without understanding the associated extended attributes.

### -field EaNameLength

The length in bytes of the <b>EaName</b> array. This value does not include a null-terminator to <b>EaName</b>.

### -field EaValueLength

The length in bytes of each EA value in the array.

### -field EaName

An array of characters naming the EA for this entry.

## -remarks

This structure is longword-aligned. If a set of <b>FILE_FULL_EA_INFORMATION</b> entries is buffered, <b>NextEntryOffset</b> value in each entry, except the last, falls on a longword boundary. 

The value(s) associated with each entry follows the <b>EaName</b> array. That is, an EA's values are located at <b>EaName</b> + (<b>EaNameLength</b> + 1).

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>


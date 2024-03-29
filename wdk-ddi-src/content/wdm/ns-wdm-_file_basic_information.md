---
UID: NS:wdm._FILE_BASIC_INFORMATION
title: FILE_BASIC_INFORMATION (wdm.h)
description: The FILE_BASIC_INFORMATION structure contains timestamps and basic attributes of a file. It is used as an argument to routines that query or set file information.
old-location: kernel\file_basic_information.htm
tech.root: kernel
ms.date: 05/18/2021
author: lorihollasch
keywords: ["FILE_BASIC_INFORMATION structure"]
ms.keywords: "*PFILE_BASIC_INFORMATION, FILE_BASIC_INFORMATION, FILE_BASIC_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_BASIC_INFORMATION, PFILE_BASIC_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_BASIC_INFORMATION, kernel.file_basic_information, kstruct_b_3de98e8c-d842-45e9-a9bd-948276ef1b87.xml, wdm/FILE_BASIC_INFORMATION, wdm/PFILE_BASIC_INFORMATION"
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
req.typenames: FILE_BASIC_INFORMATION, *PFILE_BASIC_INFORMATION
f1_keywords:
 - _FILE_BASIC_INFORMATION
 - wdm/_FILE_BASIC_INFORMATION
 - PFILE_BASIC_INFORMATION
 - wdm/PFILE_BASIC_INFORMATION
 - FILE_BASIC_INFORMATION
 - wdm/FILE_BASIC_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _FILE_BASIC_INFORMATION
 - PFILE_BASIC_INFORMATION
 - FILE_BASIC_INFORMATION
---

# FILE_BASIC_INFORMATION structure

## -description

The **FILE_BASIC_INFORMATION** structure contains timestamps and basic attributes of a file. It is used as an argument to routines that query or set file information.

## -struct-fields

### -field CreationTime

Specifies the time that the file was created.

### -field LastAccessTime

Specifies the time that the file was last accessed.

### -field LastWriteTime

Specifies the time that the file was last written to.

### -field ChangeTime

Specifies the last time the file was changed.

### -field FileAttributes

Specifies one or more FILE_ATTRIBUTE_*XXX* flags. For descriptions of these flags, see [File Attribute Constants](/windows/win32/fileio/file-attribute-constants) in the Microsoft Windows SDK.

## -remarks

The FILE_ATTRIBUTE_NORMAL flag cannot be set or returned in combination with any other attributes. All other **FileAttributes** values override this attribute.

Time values **CreationTime**, **LastAccessTime**, **LastWriteTime**, and **ChangeTime** are expressed in absolute system time format. Absolute system time is the number of 100-nanosecond intervals since the start of the year 1601 in the Gregorian calendar.

If you specify a value of zero for any of the *Xxx***Time** members of the **FILE_BASIC_INFORMATION** structure, the [ZwSetInformationFile](../ntifs/nf-ntifs-ntsetinformationfile.md) function keeps a file's current setting for that time.

The file system updates the values of the **LastAccessTime**, **LastWriteTime**, and **ChangeTime** members as appropriate after an I/O operation is performed on a file. A driver or application can request that the file system not update one or more of these members for I/O operations that are performed on the caller's file handle by setting the appropriate members to -1. The caller can set one, all, or any other combination of these three members to -1. Only the members that are set to -1 will be unaffected by I/O operations on the file handle; the other members will be updated as appropriate. On NTFS and ReFS systems, time stamp updates on the file handle can be restored by setting the appropriate member(s) to -2.

To set the members of this structure, the caller must have FILE_WRITE_ATTRIBUTES access to the file.

## -see-also

[KeQuerySystemTime](./nf-wdm-kequerysystemtime-r1.md)

[ZwCreateFile](../ntifs/nf-ntifs-ntcreatefile.md)

[ZwQueryInformationFile](../ntifs/nf-ntifs-ntqueryinformationfile.md)

[ZwSetInformationFile](../ntifs/nf-ntifs-ntsetinformationfile.md)

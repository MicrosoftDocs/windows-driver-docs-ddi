---
UID: NS:ntifs._FILE_ALL_INFORMATION
title: _FILE_ALL_INFORMATION (ntifs.h)
description: The FILE_ALL_INFORMATION structure is a container for several FILE_XXX_INFORMATION structures.
old-location: kernel\file_all_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["FILE_ALL_INFORMATION structure"]
ms.keywords: "*PFILE_ALL_INFORMATION, FILE_ALL_INFORMATION, FILE_ALL_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ALL_INFORMATION, PFILE_ALL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ALL_INFORMATION, kernel.file_all_information, kstruct_b_24c6b1da-76d1-46a9-838d-bb19af21d6f8.xml, ntifs/FILE_ALL_INFORMATION, ntifs/PFILE_ALL_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows XP and later versions of Windows.
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
req.typenames: FILE_ALL_INFORMATION, *PFILE_ALL_INFORMATION
f1_keywords:
 - _FILE_ALL_INFORMATION
 - ntifs/_FILE_ALL_INFORMATION
 - PFILE_ALL_INFORMATION
 - ntifs/PFILE_ALL_INFORMATION
 - FILE_ALL_INFORMATION
 - ntifs/FILE_ALL_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _FILE_ALL_INFORMATION
 - PFILE_ALL_INFORMATION
 - FILE_ALL_INFORMATION
---

# _FILE_ALL_INFORMATION structure


## -description

The <b>FILE_ALL_INFORMATION</b> structure is a container for several <b>FILE_<i>XXX</i>_INFORMATION</b> structures.

## -struct-fields

### -field BasicInformation

Contains basic information about the file, which includes the file attributes and the file creation time. This member is a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a> structure.

### -field StandardInformation

Contains standard information about a file, which includes the file allocation size, the end-of-file offset, and whether the file is a directory. This member is a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information">FILE_STANDARD_INFORMATION</a> structure.

### -field InternalInformation

Contains the 8-byte file reference number for the file. This member is a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_internal_information">FILE_INTERNAL_INFORMATION</a> structure.

### -field EaInformation

Specifies the size of the extended attributes of the file. This member is a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_ea_information">FILE_EA_INFORMATION</a> structure.

### -field AccessInformation

Specifies the client's access rights to the file. This member is a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_access_information">FILE_ACCESS_INFORMATION</a> structure.

### -field PositionInformation

Specifies the current file position. This member is a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a> structure.

### -field ModeInformation

Specifies the access mode in which the file was created or opened. This member is a <a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_mode_information">FILE_MODE_INFORMATION</a> structure.

### -field AlignmentInformation

Specifies the device's memory address alignment requirement for data transfers. This member is a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information">FILE_ALIGNMENT_INFORMATION</a> structure.

### -field NameInformation

Contains the file name. This member is a <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a> structure. This structure contains the first character in the file name string. The additional characters in the file name string immediately follow the structure. To accommodate the full file name, the buffer that is allocated to contain a <b>FILE_ALL_INFORMATION</b> structure must be large enough to contain both the structure and the part of the file name string that follows the structure.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> routine.

<b>FILE_ALL_INFORMATION</b> combines several file-information structures into a single structure to reduce the number of queries that are required to obtain information about a file.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_access_information">FILE_ACCESS_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_alignment_information">FILE_ALIGNMENT_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_basic_information">FILE_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_ea_information">FILE_EA_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_internal_information">FILE_INTERNAL_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_mode_information">FILE_MODE_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_name_information">FILE_NAME_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_position_information">FILE_POSITION_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_standard_information">FILE_STANDARD_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>


---
UID: NS:ntifs._FILE_KNOWN_FOLDER_INFORMATION
tech.root: ifsk
title: FILE_KNOWN_FOLDER_INFORMATION
ms.date: 09/24/2021
targetos: Windows
description: Learn more about the FILE_KNOWN_FOLDER_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: FILE_KNOWN_FOLDER_INFORMATION, *PFILE_KNOWN_FOLDER_INFORMATION
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FILE_KNOWN_FOLDER_INFORMATION
 - PFILE_KNOWN_FOLDER_INFORMATION
 - FILE_KNOWN_FOLDER_INFORMATION
f1_keywords:
 - _FILE_KNOWN_FOLDER_INFORMATION
 - ntifs/_FILE_KNOWN_FOLDER_INFORMATION
 - PFILE_KNOWN_FOLDER_INFORMATION
 - ntifs/PFILE_KNOWN_FOLDER_INFORMATION
 - FILE_KNOWN_FOLDER_INFORMATION
 - ntifs/FILE_KNOWN_FOLDER_INFORMATION
dev_langs:
 - c++
---

## -description

The **FILE_KNOWN_FOLDER_INFORMATION** structure contains information about a known folder (for example, *Documents*, *Downloads*, *Pictures*, and so forth).

## -struct-fields

### -field Type

A [**FILE_KNOWN_FOLDER_TYPE**](ne-ntifs-file_known_folder_type.md) value that identifies the known folder.

## -remarks

When a function is called to set or query information for a file object with a [**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md) value of **FileKnownFolderInformation**, that function’s **FileInformation** parameter points to a caller-allocated **FILE_KNOWN_FOLDER_INFORMATION** structure. The **See Also** section lists a few such set/query functions.

## -see-also

[**FILE_INFORMATION_CLASS**](../wdm/ne-wdm-_file_information_class.md)

[**FILE_KNOWN_FOLDER_TYPE**](ne-ntifs-file_known_folder_type.md)

[**NtQueryInformationFile**](nf-ntifs-ntqueryinformationfile.md)

[**NtSetInformationFile**](nf-ntifs-ntsetinformationfile.md)

[**ZwQueryInformationFile**](../wdm/nf-wdm-zwqueryinformationfile)

[**ZwSetInformationFile**](../wdm/nf-wdm-zwsetinformationfile.md)

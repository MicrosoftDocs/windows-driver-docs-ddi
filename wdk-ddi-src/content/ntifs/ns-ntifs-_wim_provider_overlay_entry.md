---
UID: NS:ntifs._WIM_PROVIDER_OVERLAY_ENTRY
title: WIM_PROVIDER_OVERLAY_ENTRY (ntifs.h)
description: Learn more about the WIM_PROVIDER_OVERLAY_ENTRY structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["WIM_PROVIDER_OVERLAY_ENTRY structure"]
ms.keywords: "*PWIM_PROVIDER_OVERLAY_ENTRY, PWIM_PROVIDER_OVERLAY_ENTRY, PWIM_PROVIDER_OVERLAY_ENTRY structure pointer [Installable File System Drivers], WIM_BOOT_NOT_OS_WIM, WIM_BOOT_OS_WIM, WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE, WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED, WIM_PROVIDER_OVERLAY_ENTRY, WIM_PROVIDER_OVERLAY_ENTRY structure [Installable File System Drivers], _WIM_PROVIDER_OVERLAY_ENTRY, ifsk.wim_provider_overlay_entry, ntifs/PWIM_PROVIDER_OVERLAY_ENTRY, ntifs/WIM_PROVIDER_OVERLAY_ENTRY"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1 Update
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
req.typenames: WIM_PROVIDER_OVERLAY_ENTRY, *PWIM_PROVIDER_OVERLAY_ENTRY
f1_keywords:
 - _WIM_PROVIDER_OVERLAY_ENTRY
 - ntifs/_WIM_PROVIDER_OVERLAY_ENTRY
 - PWIM_PROVIDER_OVERLAY_ENTRY
 - ntifs/PWIM_PROVIDER_OVERLAY_ENTRY
 - WIM_PROVIDER_OVERLAY_ENTRY
 - ntifs/WIM_PROVIDER_OVERLAY_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WIM_PROVIDER_OVERLAY_ENTRY
 - PWIM_PROVIDER_OVERLAY_ENTRY
 - WIM_PROVIDER_OVERLAY_ENTRY
---

# WIM_PROVIDER_OVERLAY_ENTRY structure

## -description

The **WIM_PROVIDER_OVERLAY_ENTRY** structure contains the Windows Image Format (WIM) file configuration information for a data source entry. It is used to identify specific WIM file names and indices that supply data to externally backed files on a volume.

## -struct-fields

### -field NextEntryOffset

The offset to the next **WIM_PROVIDER_OVERLAY_ENTRY** structure returned in the enumeration. Set to 0 if there are no further entries.

### -field DataSourceId

The specific identifier an overlay entry. A single WIM GUID, such as in the **WimGuid** member, may have multiple  data source identifiers.

### -field WimGuid

A unique identifier of a WIM file.

### -field WimFileNameOffset

The offset, in bytes, from the beginning of this structure of the file name for the WIM file to add as a backing source. The file name is a NULL terminated string of **WCHAR** character values.

### -field WimType

The type of WIM file set as a backing source. The WIM file type is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| WIM_BOOT_OS_WIM     | The WIM file contains Windows system files. |
| WIM_BOOT_NOT_OS_WIM | The WIM file contains non-operating system files. |

### -field WimIndex

The index of the image in the WIM file specified at **WimFileNameOffset**.

### -field Flags

The status flags for the WIM provider. Set to 0 when active. Otherwise **Flags** is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| WIM_PROVIDER_EXTERNAL_FLAG_NOT_ACTIVE | The WIM provider is not active, which can occur when the WIM file is not found. In this case, the WIM file will not be recovered. |
| WIM_PROVIDER_EXTERNAL_FLAG_SUSPENDED  | The provider is dismounted. Recovery will be attempted. |

## -see-also

[**FSCTL_ENUM_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-enum-overlay)

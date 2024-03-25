---
UID: NS:ntifs._WIM_PROVIDER_ADD_OVERLAY_INPUT
title: WIM_PROVIDER_ADD_OVERLAY_INPUT (ntifs.h)
description: Learn more about the WIM_PROVIDER_ADD_OVERLAY_INPUT structure.
tech.root: ifsk
ms.date: 06/23/2023
keywords: ["WIM_PROVIDER_ADD_OVERLAY_INPUT structure"]
ms.keywords: "*PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_BOOT_NOT_OS_WIM, WIM_BOOT_OS_WIM, WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_ADD_OVERLAY_INPUT, ifsk.wim_provider_add_overlay_input, ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT, ntifs/WIM_PROVIDER_ADD_OVERLAY_INPUT"
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
req.typenames: WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT
f1_keywords:
 - _WIM_PROVIDER_ADD_OVERLAY_INPUT
 - ntifs/_WIM_PROVIDER_ADD_OVERLAY_INPUT
 - PWIM_PROVIDER_ADD_OVERLAY_INPUT
 - ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT
 - WIM_PROVIDER_ADD_OVERLAY_INPUT
 - ntifs/WIM_PROVIDER_ADD_OVERLAY_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WIM_PROVIDER_ADD_OVERLAY_INPUT
 - PWIM_PROVIDER_ADD_OVERLAY_INPUT
 - WIM_PROVIDER_ADD_OVERLAY_INPUT
---

# WIM_PROVIDER_ADD_OVERLAY_INPUT structure

## -description

The **WIM_PROVIDER_ADD_OVERLAY_INPUT** structure is used to add a new Windows Image File (WIM) data source to the WIM provider.

## -struct-fields

### -field WimType

The type of WIM file set as a backing source. The WIM file type is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| WIM_BOOT_OS_WIM     | The WIM file contains Windows system files. |
| WIM_BOOT_NOT_OS_WIM | The WIM file contains non-operating system files. |

### -field WimIndex

The index of the image in the WIM file whose filename is specified at **WimFileNameOffset**.

### -field WimFileNameOffset

The offset, in bytes, from the beginning of this structure of the file name for the WIM file to add as a backing source. The file name is a string of **WCHAR** character values.

### -field WimFileNameLength

The length, in bytes, of the file name at found at  **WimFileNameOffset**.

## -remarks

The WIM file name is included immediately following **WIM_PROVIDER_ADD_OVERLAY_INPUT** in the system buffer for a [**FSCTL_ADD_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-add-overlay) control request. The **WimFileNameOffset** member is set to **sizeof**(WIM_PROVIDER_ADD_OVERLAY_INPUT).

The WIM file name includes a terminating NULL character. **WimFileNameLength** contains the length of the file name excluding the terminating NULL.

## -see-also

[**FSCTL_ADD_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-add-overlay)

[**FSCTL_REMOVE_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-remove-overlay)

[**FSCTL_SUSPEND_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-suspend-overlay)

[**FSCTL_UPDATE_OVERLAY**](/windows-hardware/drivers/ifs/fsctl-update-overlay)

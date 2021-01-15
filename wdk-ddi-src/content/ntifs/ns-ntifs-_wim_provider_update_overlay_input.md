---
UID: NS:ntifs._WIM_PROVIDER_UPDATE_OVERLAY_INPUT
title: _WIM_PROVIDER_UPDATE_OVERLAY_INPUT (ntifs.h)
description: A current Windows Image File (WIM) data source is updated with a new WIM file using the FSCTL_UPDATE_OVERLAY control request with a WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_update_overlay_input.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure"]
ms.keywords: "*PWIM_PROVIDER_UPDATE_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT structure [Installable File System Drivers], WIM_PROVIDER_UPDATE_OVERLAY_INPUT, WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_UPDATE_OVERLAY_INPUT, ifsk.wim_provider_update_overlay_input, ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT, ntifs/WIM_PROVIDER_ADD_OVERLAY_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
req.typenames: WIM_PROVIDER_UPDATE_OVERLAY_INPUT, *PWIM_PROVIDER_UPDATE_OVERLAY_INPUT
f1_keywords:
 - _WIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - ntifs/_WIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - PWIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - ntifs/PWIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - WIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - ntifs/WIM_PROVIDER_UPDATE_OVERLAY_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _WIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - PWIM_PROVIDER_UPDATE_OVERLAY_INPUT
 - WIM_PROVIDER_UPDATE_OVERLAY_INPUT
---

# _WIM_PROVIDER_UPDATE_OVERLAY_INPUT structure


## -description

A current Windows Image File (WIM) data source is updated with a new WIM file using the <a href="/windows-hardware/drivers/ifs/fsctl-update-overlay">FSCTL_UPDATE_OVERLAY</a> control request with a <b>WIM_PROVIDER_UPDATE_OVERLAY_INPUT</b> structure.

## -struct-fields

### -field DataSourceId

An identifier value for the WIM file data source to update.

### -field WimFileNameOffset

The offset, in bytes, from the beginning of this structure of the file name for the WIM file to add as a backing source. The file name is a string of <b>WCHAR</b> character values.

### -field WimFileNameLength

The length, in bytes, of the file name at found at  <b>WimFileNameOffset</b>.

## -remarks

The WIM file name is included immediately following <b>WIM_PROVIDER_UPDATE_OVERLAY_INPUT</b> in the system buffer for a <a href="/windows-hardware/drivers/ifs/fsctl-update-overlay">FSCTL_UPDATE_OVERLAY</a> control request. The <b>WimFileNameOffset</b> member is set to <b>sizeof</b>(<b>WIM_PROVIDER_UPDATE_OVERLAY_INPUT</b>).

The WIM file name includes a terminating NULL character. <b>WimFileNameLength</b> contains the length of the file name excluding the terminating NULL.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-add-overlay">FSCTL_ADD_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-remove-overlay">FSCTL_REMOVE_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-suspend-overlay">FSCTL_SUSPEND_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-update-overlay">FSCTL_UPDATE_OVERLAY</a>


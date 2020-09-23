---
UID: NS:ntifs._WIM_PROVIDER_ADD_OVERLAY_INPUT
title: _WIM_PROVIDER_ADD_OVERLAY_INPUT (ntifs.h)
description: A new Windows Image File (WIM) data source is added to the WIM provider with the WIM_PROVIDER_ADD_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_add_overlay_input.htm
tech.root: ifsk
ms.assetid: 75C95941-367D-4A7F-A121-AF2BF9EFE28E
ms.date: 04/16/2018
keywords: ["WIM_PROVIDER_ADD_OVERLAY_INPUT structure"]
ms.keywords: "*PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT, PWIM_PROVIDER_ADD_OVERLAY_INPUT structure pointer [Installable File System Drivers], WIM_BOOT_NOT_OS_WIM, WIM_BOOT_OS_WIM, WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT structure [Installable File System Drivers], _WIM_PROVIDER_ADD_OVERLAY_INPUT, ifsk.wim_provider_add_overlay_input, ntifs/PWIM_PROVIDER_ADD_OVERLAY_INPUT, ntifs/WIM_PROVIDER_ADD_OVERLAY_INPUT"
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
 - WIM_PROVIDER_ADD_OVERLAY_INPUT
---

# _WIM_PROVIDER_ADD_OVERLAY_INPUT structure


## -description

A new Windows Image File (WIM) data source is added to the WIM provider with the <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> structure.

## -struct-fields

### -field WimType

The type of WIM file set as a backing source. The WIM file type is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="_WIM_BOOT_OS_WIM"></a><a id="_wim_boot_os_wim"></a><dl>
<dt><b> WIM_BOOT_OS_WIM</b></dt>
</dl>
</td>
<td width="60%">
The WIM file contains Windows system files.

</td>
</tr>
<tr>
<td width="40%"><a id="_WIM_BOOT_NOT_OS_WIM"></a><a id="_wim_boot_not_os_wim"></a><dl>
<dt><b> WIM_BOOT_NOT_OS_WIM</b></dt>
</dl>
</td>
<td width="60%">
The WIM file contains non-operating system files.

</td>
</tr>
</table>

### -field WimIndex

The index of the image in the WIM file whose filename is specified at <b>WimFileNameOffset</b>.

### -field WimFileNameOffset

The offset, in bytes, from the beginning of this structure of the file name for the WIM file to add as a backing source. The file name is a string of <b>WCHAR</b> character values.

### -field WimFileNameLength

The length, in bytes, of the file name at found at  <b>WimFileNameOffset</b>.

## -remarks

The WIM file name is included immediately following <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> in the system buffer for a <a href="/windows-hardware/drivers/ifs/fsctl-add-overlay">FSCTL_ADD_OVERLAY</a> control request. The <b>WimFileNameOffset</b> member is set to <b>sizeof</b>(WIM_PROVIDER_ADD_OVERLAY_INPUT).

The WIM file name includes a terminating NULL character. <b>WimFileNameLength</b> contains the length of the file name excluding the terminating NULL.

## -see-also

<a href="/windows-hardware/drivers/ifs/fsctl-add-overlay">FSCTL_ADD_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-remove-overlay">FSCTL_REMOVE_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-suspend-overlay">FSCTL_SUSPEND_OVERLAY</a>



<a href="/windows-hardware/drivers/ifs/fsctl-update-overlay">FSCTL_UPDATE_OVERLAY</a>
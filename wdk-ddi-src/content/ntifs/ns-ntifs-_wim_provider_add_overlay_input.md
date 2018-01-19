---
UID: NS:ntifs._WIM_PROVIDER_ADD_OVERLAY_INPUT
title: _WIM_PROVIDER_ADD_OVERLAY_INPUT
author: windows-driver-content
description: A new Windows Image File (WIM) data source is added to the WIM provider with the WIM_PROVIDER_ADD_OVERLAY_INPUT structure.
old-location: ifsk\wim_provider_add_overlay_input.htm
old-project: ifsk
ms.assetid: 75C95941-367D-4A7F-A121-AF2BF9EFE28E
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _WIM_PROVIDER_ADD_OVERLAY_INPUT, WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WIM_PROVIDER_ADD_OVERLAY_INPUT
req.alt-loc: ntifs.h
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
req.typenames: WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT
---

# _WIM_PROVIDER_ADD_OVERLAY_INPUT structure



## -description
A new Windows Image File (WIM) data source is added to the WIM provider with the <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> structure.



## -syntax

````
typedef struct _WIM_PROVIDER_ADD_OVERLAY_INPUT {
  ULONG WimType;
  ULONG WimIndex;
  ULONG WimFileNameOffset;
  ULONG WimFileNameLength;
} WIM_PROVIDER_ADD_OVERLAY_INPUT, *PWIM_PROVIDER_ADD_OVERLAY_INPUT;
````


## -struct-fields

### -field WimType

The type of WIM file set as a backing source. The WIM file type is set to one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field  WIM_BOOT_OS_WIM

</td>
<td width="60%">
The WIM file contains Windows system files.

</td>
</tr>
<tr>

### -field  WIM_BOOT_NOT_OS_WIM

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
The WIM file name is included immediately following <b>WIM_PROVIDER_ADD_OVERLAY_INPUT</b> in the system buffer for a <a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a> control request. The <b>WimFileNameOffset</b> member is set to <b>sizeof</b>(WIM_PROVIDER_ADD_OVERLAY_INPUT).

The WIM file name includes a terminating NULL character. <b>WimFileNameLength</b> contains the length of the file name excluding the terminating NULL.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632437">FSCTL_ADD_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632442">FSCTL_REMOVE_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt426735">FSCTL_SUSPEND_OVERLAY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn632445">FSCTL_UPDATE_OVERLAY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WIM_PROVIDER_ADD_OVERLAY_INPUT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:fltkernel.FltGetVolumeName
title: FltGetVolumeName function
author: windows-driver-content
description: The FltGetVolumeName routine gets the volume name for a given volume.
old-location: ifsk\fltgetvolumename.htm
old-project: ifsk
ms.assetid: 50815b33-d417-4499-9423-f65697396200
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltGetVolumeName
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltGetVolumeName
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
req.typenames: EXpsFontRestriction
---

# FltGetVolumeName function



## -description
The <b>FltGetVolumeName</b> routine gets the volume name for a given volume. 



## -syntax

````
NTSTATUS FltGetVolumeName(
  _In_        PFLT_VOLUME     Volume,
  _Inout_opt_ PUNICODE_STRING VolumeName,
  _Out_opt_   PULONG          BufferSizeNeeded
);
````


## -parameters

### -param Volume [in]

An opaque pointer for the volume. 


### -param VolumeName [in, out, optional]

A pointer to a caller-allocated <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the volume's non-persistent device object name (for example, "\Device\HarddiskVolume1") when STATUS_SUCCESS is returned.  Be aware that pool for the <b>Buffer</b> member of this structure is caller-allocated also. This parameter is optional and can be <b>NULL</b>. However, <i>VolumeName</i> must be non-<b>NULL</b> if <i>BufferSizeNeeded</i> is <b>NULL</b>.


### -param BufferSizeNeeded [out, optional]

A pointer to a caller-allocated variable that receives the size, in bytes, of the requested volume name.   If <b>FltGetVolumeName</b> returns STATUS_BUFFER_TOO_SMALL, <i>BufferSizeNeeded</i> receives the size of the buffer (pointed to by the <b>Buffer</b> member of the UNICODE_STRING structure) that is required for this routine to succeed.

<i>BufferSizeNeeded</i> is optional and can be <b>NULL</b>. However, <i>BufferSizeNeeded</i> must be non-<b>NULL</b> if <i>VolumeName</i> is <b>NULL</b>.


## -returns
<b>FltGetVolumeName</b> returns one of the following NTSTATUS values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The UNICODE_STRING structure, pointed to by <i>VolumeName</i>, contains the name of the volume in the <b>Buffer</b> member for the structure and the length of the name, in bytes, in the <b>Length</b> member.
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The <b>Buffer</b> member of the UNICODE_STRING structure, pointed to by <i>VolumeName</i>, is too small (as indicated by its <b>MaximumLength</b> member) to contain the entire volume name.  This is an error code.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><i>VolumeName</i> and <i>BufferSizeNeeded</i> are both <b>NULL</b>. This is an error code. 

 


## -remarks
For this routine to succeed, the <b>Buffer</b> member of the UNICODE_STRING structure (pointed to by <i>VolumeName</i>) must be large enough, as indicated by its <b>MaximumLength</b> member, to contain the entire volume name string.  The following pseudocode shows one possible method to successfully acquire a volume name:

Allocate <code>VolumeNameSize</code> bytes of pool for <b>Buffer</b> and set <b>MaximumLength</b> to <code>VolumeNameSize</code>.

<code>VolumeNameStruct.Buffer</code> contains the Unicode volume name string, which is <code>VolumeNameStruct.Length</code> bytes in length.

To get the volume GUID name for a given volume, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>. 

To get an opaque volume pointer for a volume with a given name, call <a href="..\fltkernel\nf-fltkernel-fltgetvolumefromname.md">FltGetVolumeFromName</a>. 

For more information about how to name a volume, see <a href="https://msdn.microsoft.com/fb37f862-70d6-4514-b481-16f664346422">Supporting Mount Manager Requests in a Storage Class Driver</a>. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540492">FilterGetDosName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumefromname.md">FltGetVolumeFromName</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetvolumeguidname.md">FltGetVolumeGuidName</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltGetVolumeName routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


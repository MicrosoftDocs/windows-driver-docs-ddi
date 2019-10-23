---
UID: NF:fltkernel.FltGetVolumeName
title: FltGetVolumeName function (fltkernel.h)
description: The FltGetVolumeName routine gets the volume name for a given volume.
old-location: ifsk\fltgetvolumename.htm
tech.root: ifsk
ms.assetid: 50815b33-d417-4499-9423-f65697396200
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_8d8cee36-2d14-4d5e-b95a-065a50d83f15.xml, FltGetVolumeName, FltGetVolumeName routine [Installable File System Drivers], fltkernel/FltGetVolumeName, ifsk.fltgetvolumename
ms.topic: function
f1_keywords:
 - "fltkernel/FltGetVolumeName"
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetVolumeName
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetVolumeName function


## -description


The <b>FltGetVolumeName</b> routine gets the volume name for a given volume. 


## -parameters




### -param Volume [in]

An opaque pointer for the volume. 


### -param VolumeName [in, out, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the volume's non-persistent device object name (for example, "\Device\HarddiskVolume1") when STATUS_SUCCESS is returned.  Be aware that pool for the <b>Buffer</b> member of this structure is caller-allocated also. This parameter is optional and can be <b>NULL</b>. However, <i>VolumeName</i> must be non-<b>NULL</b> if <i>BufferSizeNeeded</i> is <b>NULL</b>.


### -param BufferSizeNeeded [out, optional]

A pointer to a caller-allocated variable that receives the size, in bytes, of the requested volume name.   If <b>FltGetVolumeName</b> returns STATUS_BUFFER_TOO_SMALL, <i>BufferSizeNeeded</i> receives the size of the buffer (pointed to by the <b>Buffer</b> member of the UNICODE_STRING structure) that is required for this routine to succeed.

<i>BufferSizeNeeded</i> is optional and can be <b>NULL</b>. However, <i>BufferSizeNeeded</i> must be non-<b>NULL</b> if <i>VolumeName</i> is <b>NULL</b>.


## -returns



<b>FltGetVolumeName</b> returns one of the following NTSTATUS values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The UNICODE_STRING structure, pointed to by <i>VolumeName</i>, contains the name of the volume in the <b>Buffer</b> member for the structure and the length of the name, in bytes, in the <b>Length</b> member.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <b>Buffer</b> member of the UNICODE_STRING structure, pointed to by <i>VolumeName</i>, is too small (as indicated by its <b>MaximumLength</b> member) to contain the entire volume name.  This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
<i>VolumeName</i> and <i>BufferSizeNeeded</i> are both <b>NULL</b>. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



For this routine to succeed, the <b>Buffer</b> member of the UNICODE_STRING structure (pointed to by <i>VolumeName</i>) must be large enough, as indicated by its <b>MaximumLength</b> member, to contain the entire volume name string.  The following pseudocode shows one possible method to successfully acquire a volume name:

<ol>
<li>Call <b>FltGetVolumeName</b> to determine the required pool for <b>Buffer</b> and the required size for <b>MaximumLength</b>.  For example:<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FltGetVolumeName(VolumePtr, NULL, &VolumeNameSize);</pre>
</td>
</tr>
</table></span></div>
</li>
<li>
Allocate <code>VolumeNameSize</code> bytes of pool for <b>Buffer</b> and set <b>MaximumLength</b> to <code>VolumeNameSize</code>.

</li>
<li>Call <b>FltGetVolumeName</b> again to acquire the volume name.  For example:<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>FltGetVolumeName(VolumePtr, &VolumeNameStruct, NULL);</pre>
</td>
</tr>
</table></span></div>
<code>VolumeNameStruct.Buffer</code> contains the Unicode volume name string, which is <code>VolumeNameStruct.Length</code> bytes in length.

</li>
</ol>
To get the volume GUID name for a given volume, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumeguidname">FltGetVolumeGuidName</a>. 

To get an opaque volume pointer for a volume with a given name, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefromname">FltGetVolumeFromName</a>. 

For more information about how to name a volume, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver">Supporting Mount Manager Requests in a Storage Class Driver</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/fltuser/nf-fltuser-filtergetdosname">FilterGetDosName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumefromname">FltGetVolumeFromName</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetvolumeguidname">FltGetVolumeGuidName</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 


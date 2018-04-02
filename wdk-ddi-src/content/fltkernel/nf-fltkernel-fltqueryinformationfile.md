---
UID: NF:fltkernel.FltQueryInformationFile
title: FltQueryInformationFile function
author: windows-driver-content
description: FltQueryInformationFile retrieves information for a given file.
old-location: ifsk\fltqueryinformationfile.htm
old-project: ifsk
ms.assetid: f80750fb-4561-4617-bc54-1360b2e93a68
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_p_to_z_f6c70c3b-4b99-4ae9-ba01-789c4d3ab1c3.xml, FltQueryInformationFile, FltQueryInformationFile function [Installable File System Drivers], fltkernel/FltQueryInformationFile, ifsk.fltqueryinformationfile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltQueryInformationFile
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltQueryInformationFile function


## -description


<b>FltQueryInformationFile</b> retrieves information for a given file. 


## -parameters




### -param Instance [in]

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. 


### -param FileObject [in]

File object pointer for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param FileInformation [out]

Pointer to a caller-allocated buffer that receives information about the file. The <i>FileInformationClass</i> parameter specifies the type of information. This parameter is required and cannot be <b>NULL</b>. 


### -param Length [in]

Size, in bytes, of the <i>FileInformation</i> buffer. 


### -param FileInformationClass [in]

Type of file information to be returned. One of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FileAllInformation</b>

</td>
<td>
Return a FILE_ALL_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileAttributeTagInformation</b>

</td>
<td>
Return a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545750">FILE_ATTRIBUTE_TAG_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileBasicInformation</b>

</td>
<td>
Return a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545762">FILE_BASIC_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileCompressionInformation</b>

</td>
<td>
Return a FILE_COMPRESSION_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileEaInformation</b>

</td>
<td>
Return a FILE_EA_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileInternalInformation</b>

</td>
<td>
Return a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540318">FILE_INTERNAL_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileMoveClusterInformation</b>

</td>
<td>
Return a FILE_MOVE_CLUSTER_INFORMATION structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileNameInformation</b>

</td>
<td>
Return a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545817">FILE_NAME_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileNetworkOpenInformation</b>

</td>
<td>
Return a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff545822">FILE_NETWORK_OPEN_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FilePositionInformation</b>

</td>
<td>
Return a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff545848">FILE_POSITION_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileStandardInformation</b>

</td>
<td>
Return a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff545855">FILE_STANDARD_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileStreamInformation</b>

</td>
<td>
Return a single <a href="https://msdn.microsoft.com/library/windows/hardware/ff540364">FILE_STREAM_INFORMATION</a> structure for the file. 

</td>
</tr>
<tr>
<td>
<b>FileHardLinkInformation</b>

</td>
<td>
Return a <a href="https://msdn.microsoft.com/library/windows/hardware/ff728841">FILE_LINKS_INFORMATION</a> structure for the file. 

</td>
</tr>
</table>
 


### -param LengthReturned [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the information returned in the <i>FileInformation</i> buffer. This parameter is optional and can be <b>NULL</b>. 


## -returns



<b>FltQueryInformationFile</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_VOLUME_DISMOUNTED</b></dt>
</dl>
</td>
<td width="60%">
The file resides on a volume that is not currently mounted. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



A minifilter driver calls <b>FltQueryInformationFile</b> to retrieve information for a given file. The file must currently be open. 

<b>FltQueryInformationFile</b> returns zero in any member of a FILE_<i>XXX</i>_INFORMATION structure that is not supported by a particular file system. 

Callers of <b>FltQueryInformationFile</b> must be running at IRQL = PASSIVE_LEVEL and <a href="https://msdn.microsoft.com/0578df31-1467-4bad-ba62-081d61278deb">with APCs enabled</a>.

<div class="alert"><b>Note</b>  Before calling this routine, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>.  If <b>IoGetTopLevelIrp</b> returns a non-<b>NULL</b> value, do not call the routine as this can cause a system deadlock.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545740">FILE_ALIGNMENT_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545750">FILE_ATTRIBUTE_TAG_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545762">FILE_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540318">FILE_INTERNAL_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff728841">FILE_LINKS_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545817">FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545822">FILE_NETWORK_OPEN_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545848">FILE_POSITION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545855">FILE_STANDARD_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540364">FILE_STREAM_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543446">FltQueryVolumeInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544516">FltSetInformationFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567052">ZwQueryInformationFile</a>
 

 


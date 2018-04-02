---
UID: NF:fltkernel.FltGetDestinationFileNameInformation
title: FltGetDestinationFileNameInformation function
author: windows-driver-content
description: The FltGetDestinationFileNameInformation routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created.
old-location: ifsk\fltgetdestinationfilenameinformation.htm
old-project: ifsk
ms.assetid: b5438802-fc96-4445-9261-5d497d2d24cc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_127cb786-b74b-4c1b-bb38-87ad3494900b.xml, FltGetDestinationFileNameInformation, FltGetDestinationFileNameInformation routine [Installable File System Drivers], fltkernel/FltGetDestinationFileNameInformation, ifsk.fltgetdestinationfilenameinformation
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltGetDestinationFileNameInformation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltGetDestinationFileNameInformation function


## -description


The <b>FltGetDestinationFileNameInformation</b> routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created. 


## -parameters




### -param Instance [in]

Opaque instance pointer for a minifilter driver instance that is attached to the volume where the file resides. 


### -param FileObject [in]

Pointer to the file object for the file. This parameter is required and cannot be <b>NULL</b>. 


### -param RootDirectory [in, optional]

<b>Link operations:</b> If the link is to be created in the same directory as the file that is being linked to, or if the <i>FileName</i> parameter contains the full pathname for the link to be created, this parameter is <b>NULL</b>. Otherwise it is a handle for the directory where the link is to be created. 

<b>Rename operations:</b> If the file is not being moved to a different directory, or if the <i>FileName</i> parameter contains the full pathname, this parameter is <b>NULL</b>. Otherwise it is a handle for the directory where the file resides after it is renamed. 


### -param FileName [in]

<b>Link operations:</b> Pointer to a wide-character string containing the name to be assigned to the newly created link. 

<b>Rename operations:</b> Pointer to a wide-character string containing the new name for the file. 


### -param FileNameLength [in]

Length, in bytes, of the wide-character string that <i>FileName </i>points to. 


### -param NameOptions [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a> value containing flags that specify the format of the name information to be returned, as well as the query method that the Filter Manager is to use. This parameter is required and cannot be <b>NULL</b>. 

Following are the name format flag values. Only one of the following flags can be specified. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_NORMALIZED

</td>
<td>
The <i>FileName</i> parameter receives the normalized destination name for the file. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_OPENED

</td>
<td>
The <i>FileName</i> parameter receives the destination name for the file, based on the name that was used when the file was opened. This file name is not normalized. 

</td>
</tr>
</table>
 

Note that FLT_FILE_NAME_SHORT is not a valid flag value for this parameter. 

Following are the query method flag values. Only one of the following flags can be specified. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_DEFAULT

</td>
<td>
If it is not currently safe to query the file system for the file name, <b>FltGetDestinationFileNameInformation</b> does nothing. Otherwise, <b>FltGetDestinationFileNameInformation</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, <b>FltGetDestinationFileNameInformation</b> queries the file system and caches the result. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_CACHE_ONLY

</td>
<td>
<b>FltGetDestinationFileNameInformation</b> queries the Filter Manager's name cache for the file name information. <b>FltGetDestinationFileNameInformation</b> does not query the file system. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY

</td>
<td>
<b>FltGetDestinationFileNameInformation</b> queries the file system for the file name information. <b>FltGetDestinationFileNameInformation</b> does not query the Filter Manager's name cache, and does not cache the result of the file system query. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP

</td>
<td>
<b>FltGetDestinationFileNameInformation</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, and it is currently safe to do so, <b>FltGetDestinationFileNameInformation</b> queries the file system for the file name information and cache the result. 

</td>
</tr>
</table>
 


### -param RetFileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure containing the file name information. <b>FltGetDestinationFileNameInformation</b> allocates this structure from paged pool. This parameter is required and cannot be <b>NULL</b>. 


## -returns



<b>FltGetDestinationFileNameInformation</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INVALID_NAME_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
This return value means one of the following: 

<ul>
<li>
<b>FltGetDestinationFileNameInformation</b> cannot get file name information if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information about this issue, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>.) 

</li>
<li>
FLT_FILE_NAME_SHORT was specified for the name format flag in the <i>NameOptions</i> parameter. 

</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltGetDestinationFileNameInformation</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>NameOptions</i> parameter. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">
The destination path name contains a mount point that resolves to a volume other than the one where the file resides. (Because a rename or hard-link-creation operation can only be performed within a volume and not across volumes, the operation fails.) This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<b>FltGetDestinationFileNameInformation</b> returns the file name information in either normalized or "opened file" format. For more information on these formats, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure. 

The file object pointer that is passed for the <i>FileObject</i> parameter must be either the <b>FileObject</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a> structure for the operation or the <b>Data-&gt;Iopb-&gt;TargetFileObject</b> pointer for the operation, where <b>Data</b> is the callback data structure for the operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). The file object pointer cannot be the <b>Data-&gt;Iopb-&gt;Parameters.SetFileInformation.FileObject</b> member, because this field is not used uniformly across file systems. 

If the user opened the file by using the file ID but does not have traverse privilege for the entire path, <b>FltGetDestinationFileNameInformation</b> returns only the portion of the path that the user has privilege for. 

A rename or hard-link-creation operation can only be performed within a volume and not across volumes. Therefore, such an operation fails if the destination path name contains a mount point that resolves to a volume other than the one where the file resides. For more information about rename operations, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540344">FILE_RENAME_INFORMATION</a> structure. For more information about hard-link creation operations, see the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540324">FILE_LINK_INFORMATION</a> structures. 

After a successful call to <b>FltGetDestinationFileNameInformation</b>, the caller is responsible for releasing the pointer returned in the <i>RetFileNameInformation</i> parameter when it is no longer needed by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>. 

The caller must not modify the contents of the structure returned in the <i>RetFileNameInformation</i> parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it. 

In create, hard-link, and rename operations, file name tunneling can cause the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine to be invalidated. If a minifilter driver retrieves normalized file name information in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine by calling a routine such as <b>FltGetDestinationFileNameInformation</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a> from its postoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine to retrieve the correct file name information for the file. 

For more information about normalized file name information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. 

<div class="alert"><b>Note</b>    File name tunneling affects only create, hard-link, and rename operations in this way. It does not affect other I/O operations, such as read and write. </div>
<div> </div>
The following paired operations can cause the file name <i>name</i> to be tunneled: 

<ul>
<li>
delete(<i>name</i>)/create(<i>name</i>)

</li>
<li>
delete(<i>name</i>)/rename(<i>source</i>, <i>name</i>)

</li>
<li>
rename(<i>name</i>, <i>newname</i>)/create(<i>name</i>)

</li>
<li>
rename(<i>name</i>, <i>newname</i>)/rename(<i>source</i>, <i>name</i>)

</li>
</ul>
For more information about file name tunneling, see <a href="http://go.microsoft.com/fwlink/p/?linkid=3100&amp;id=172190">Microsoft Knowledge Base Article 172190</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540324">FILE_LINK_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540344">FILE_RENAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544816">FLT_RELATED_OBJECTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543417">FltParseFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544301">FltReferenceFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 


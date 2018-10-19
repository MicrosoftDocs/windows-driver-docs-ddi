---
UID: NF:fltkernel.FltGetFileNameInformation
title: FltGetFileNameInformation function
author: windows-driver-content
description: The FltGetFileNameInformation routine returns name information for a file or directory.
old-location: ifsk\fltgetfilenameinformation.htm
tech.root: ifsk
ms.assetid: 707e7e83-31d8-46cf-a2ef-e53a20edaeff
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_1ce08fd0-5e23-43de-b012-dd71086282ea.xml, FltGetFileNameInformation, FltGetFileNameInformation routine [Installable File System Drivers], fltkernel/FltGetFileNameInformation, ifsk.fltgetfilenameinformation
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
-	FltGetFileNameInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetFileNameInformation function


## -description


The <b>FltGetFileNameInformation</b> routine returns name information for a file or directory. 


## -parameters




### -param CallbackData [in]

A pointer to the callback data structure for the I/O operation (<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>). This parameter is required and cannot be <b>NULL</b>. 


### -param NameOptions [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a> value containing flags that specify the format of the name information to be returned, as well as the query method that the Filter Manager is to use. (Additional flags can be used by name provider minifilter drivers to specify name query options. For more information, see <b>FLT_FILE_NAME_OPTIONS</b>.) This parameter is required and cannot be <b>NULL</b>. 

Following are the name format flag values. Only one of the following flags can be specified. (For an explanation of these formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>.) 

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
The <i>FileNameInformation</i> parameter receives the address of a structure containing the normalized name for the file. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_OPENED

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the name that was used when the file was opened. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_SHORT

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the short (8.3) name for the file. The short name consists of up to 8 characters, followed immediately by a period and up to 3 more characters. The short name for a file does not include the volume name, directory path, or stream name. 

Not valid in the pre-create path. 

</td>
</tr>
</table>
 

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
If it is not currently safe to query the file system for the file name, <b>FltGetFileNameInformation</b> does nothing. Otherwise, <b>FltGetFileNameInformation</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, <b>FltGetFileNameInformation</b> queries the file system and caches the result. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_CACHE_ONLY

</td>
<td>
FltGetFileNameInformation queries the Filter Manager's name cache for the file name information. <b>FltGetFileNameInformation</b> does not query the file system. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY

</td>
<td>
<b>FltGetFileNameInformation</b> queries the file system for the file name information. <b>FltGetFileNameInformation</b> does not query the Filter Manager's name cache, and does not cache the result of the file system query. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP

</td>
<td>
<b>FltGetFileNameInformation</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, and it is currently safe to do so, <b>FltGetFileNameInformation</b> queries the file system for the file name information and caches the result. 

</td>
</tr>
</table>
 

Name provider minifilters use the following flags to specify the properties of file name operations. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_REQUEST_FROM_CURRENT_PROVIDER

</td>
<td>
A name provider minifilter can use this flag to specify that a name query request should be redirected to itself (the name provider minifilter) rather than being satisfied by the name providers lower in the stack. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_DO_NOT_CACHE

</td>
<td>
This flag denotes that the name retrieved from this query should not be cached. Name provider minifilters use this flag as they perform intermediate queries to generate a name. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_ALLOW_QUERY_ON_REPARSE

</td>
<td>
A name provider minifilter can use this flag to specify that it is safe to query the name in the post-create path even if STATUS_REPARSE was returned. It is the caller's responsibility to ensure that the <b>FileObject-&gt;FileName</b> field was not changed. Do not use this flag with mount points or symbolic link reparse points. 

This flag is available on Microsoft Windows Server 2003 SP1 and later. This flag is also available on Windows 2000 SP4 with Update Rollup 1 and later.

</td>
</tr>
</table>
 


### -param FileNameInformation [out]

A pointer to a caller-allocated variable that receives the address of a system-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a> structure containing the file name information. <b>FltGetFileNameInformation</b> allocates this structure from paged pool. This parameter is required and cannot be <b>NULL</b>. 


## -returns



If the name information is successfully returned, <b>FltGetFileNameInformation</b> returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value such as one of the following: 

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
One of the following: 

<ul>
<li>
<b>FltGetFileNameInformation</b> cannot get file name information if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information about this issue, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>.) 

</li>
<li>
<b>FltGetFileNameInformation</b> cannot get file name information in the paging I/O path. 

</li>
<li>
<b>FltGetFileNameInformation</b> cannot get file name information in the post-close path. 

</li>
<li>
<b>FltGetFileNameInformation</b> cannot get the short name of a file in the pre-create path. 

</li>
</ul>
STATUS_FLT_INVALID_NAME_REQUEST is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltGetFileNameInformation</b> encountered a pool allocation failure. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
One of the following: 

<ul>
<li>
The <b>FileNameInformation</b> parameter cannot be <b>NULL</b>.

</li>
<li>
The <i>CallbackData</i> parameter cannot be <b>NULL</b>.

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NAME_CACHE_MISS</b></dt>
</dl>
</td>
<td width="60%">
The file name information is not found in the name cache and <i>NameOptions</i> includes FLT_FILE_NAME_QUERY_CACHE_ONLY.

-or-

The file name information is not found in the name cache when <i>NameOptions</i> includes FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP and the file name information cannot be queried from the file system.

An additional call to <b>FltGetFileNameInformation</b>  with FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY set in <i>NameOptions</i> may return the file name information.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
If the user opened the file by file ID but does not have traverse privileges for the entire path, <b>FltGetFileNameInformation</b> fails with this return value. 

STATUS_ACCESS_DENIED is an error code. 

-or-

The file is a system file with all access denied.

</td>
</tr>
</table>
 




## -remarks



<b>FltGetFileNameInformation</b> returns the requested name information for the file or directory that is represented by the file object that is the target of the I/O operation. 

For a pre-create operation, if the <b>CallbackData</b> -&gt;<b>Iopb</b> -&gt;<b>OperationFlags</b> member contains the SL_OPEN_TARGET_DIRECTORY bitwise flag, <b>FltGetFileNameInformation</b> returns the name of the containing (parent) directory for the given file. This name is the actual path that the create operation opens.

To parse the contents of the FLT_FILE_NAME_INFORMATION structure returned by <b>FltGetFileNameInformation</b>, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543417">FltParseFileNameInformation</a>. (For more information about file name formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>.) 

After a successful call to <b>FltGetFileNameInformation</b>, the caller is responsible for releasing the pointer returned in the <i>FileNameInformation</i> parameter when the pointer is no longer needed. The caller does this by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>. 

The caller must not modify the contents of the structure returned in the <i>FileNameInformation</i> parameter because this structure is cached by the Filter Manager so that all minifilter drivers can use it. 

If <b>FltGetFileNameInformation</b> is called in the preoperation callback routine for a create operation to retrieve the opened name, <b>FltGetFileNameInformation</b> succeeds even if the path to the file being opened does not exist on the volume. If <b>FltGetFileNameInformation</b> is called in the preoperation callback routine for a create operation to retrieve the normalized name, <b>FltGetFileNameInformation</b> succeeds even if the final component of the path to the file being opened does not exist on the volume.

In create, hard-link, and rename operations, file name tunneling can cause the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine to be invalidated. If a minifilter driver retrieves normalized file name information in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine by calling a routine such as <b>FltGetFileNameInformation</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a> from its postoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine to retrieve the correct file name information for the file. 

For Windows 8.1 and earlier, <b>FltGetFileNameInformation</b> can include a <a href="https://msdn.microsoft.com/41dda6f1-a6d1-4e76-94f3-a72f9e491bee">stream type</a> <i>only</i> when called from a filter’s pre-create callback.  To distinguish between a file’s default stream and metadata streams, this call should be made in the pre-create operation. The resulting stream type will remain valid across the lifetime of the file.

 Prior to Windows 8, Filter Manager obtained the normalized name for a file or directory by collecting the name information for each component of  the file path. This required multiple queries to the file system to compile the complete path. Starting with Windows 8, local file systems support the  <b>FileNormalizedNameInformation</b> file information class and only a single query is necessary to obtain the normalized name. Remote file systems may not support the <b>FileNormalizedNameInformation</b> file information class. When this is the case, a query for each component of the file path is still required to assemble the normalized name. Under certain network conditions, a full name query can require a significant amount of time to complete.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544620">FLT_CALLBACK_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543035">FltGetFileNameInformationUnsafe</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543417">FltParseFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544301">FltReferenceFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 


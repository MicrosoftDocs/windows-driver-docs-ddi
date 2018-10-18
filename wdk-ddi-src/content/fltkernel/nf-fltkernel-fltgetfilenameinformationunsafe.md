---
UID: NF:fltkernel.FltGetFileNameInformationUnsafe
title: FltGetFileNameInformationUnsafe function
author: windows-driver-content
description: The FltGetFileNameInformationUnsafe routine returns name information for an open file or directory.
old-location: ifsk\fltgetfilenameinformationunsafe.htm
tech.root: ifsk
ms.assetid: 3c5ec515-d332-4fef-8b78-b2f04a672fd7
ms.date: 4/16/2018
ms.keywords: FltApiRef_e_to_o_b6504bfd-52eb-4563-a581-ccb0b6a9afc1.xml, FltGetFileNameInformationUnsafe, FltGetFileNameInformationUnsafe routine [Installable File System Drivers], fltkernel/FltGetFileNameInformationUnsafe, ifsk.fltgetfilenameinformationunsafe
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
-	FltGetFileNameInformationUnsafe
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetFileNameInformationUnsafe function


## -description


The <b>FltGetFileNameInformationUnsafe</b> routine returns name information for an open file or directory. 


## -parameters




### -param FileObject [in]

Pointer to a file object for the file or directory. The file object must be currently open. This parameter is required and cannot be set to <b>NULL</b>. 


### -param Instance [in, optional]

Instance pointer for the caller. This parameter can be set to <b>NULL</b>. 


### -param NameOptions [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a> value containing flags that specify the format of the name information to be returned, as well as the query method to be used by the Filter Manager. This parameter is required and cannot be set to <b>NULL</b>. 

The following table describes the name format flag values. Only one of the flags can be specified. For more information about these formats, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. 

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

</td>
</tr>
</table>
 

The following table describes the query method flag values. Only one of the flags can be specified. 

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
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, <b>FltGetFileNameInformationUnsafe</b> queries the file system and caches the result. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_CACHE_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the file system. 

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the file system for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the Filter Manager's name cache, and does not cache the result of the file system query. 

</td>
</tr>
</table>
 


### -param FileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated FLT_FILE_NAME_INFORMATION structure. <b>FltGetFileNameInformationUnsafe</b> allocates this structure from paged pool. When this information is no longer needed, the caller must release the structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>. This parameter is required and cannot be set to <b>NULL</b>. 


## -returns



<b>FltGetFileNameInformationUnsafe</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 

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
The file object that the <i>FileObject</i> parameter points to is not currently open. This is an error code. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was passed for the <i>FileNameInformation</i> parameter. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



The <b>FltGetFileNameInformationUnsafe</b> routine is provided so that you can query the name of a file object outside of the context of an I/O operation on that file object. In these cases, you must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>. 

Unlike the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a> routine, <b>FltGetFileNameInformationUnsafe</b> does not protect the caller against the following types of circumstances, where querying the file system for name information can cause deadlocks: 

<ul>
<li>
When the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>. 

</li>
<li>
In the paging I/O path. 

</li>
<li>
After an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a> operation is completed. 

</li>
<li>In a preoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) or a postoperation callback routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) for any of the following operations: <dl>
<dd>IRP_MJ_ACQUIRE_FOR_CC_FLUSH </dd>
<dd>IRP_MJ_ACQUIRE_FOR_MOD_WRITE</dd>
<dd>IRP_MJ_RELEASE_FOR_CC_FLUSH</dd>
<dd>IRP_MJ_RELEASE_FOR_MOD_WRITE</dd>
<dd>IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION</dd>
</dl>
</li>
<li>
In a postoperation callback routine for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION.

</li>
</ul>
If a minifilter does not yet have a filter instance, such as in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine, it can use <code>NULL</code> for the <i>Instance</i> parameter. This allows <i>DriverEntry</i> routines to access file name information. Except for this case, a <code>NULL</code> value for the instance parameter is reserved for system use.

In create, hard-link, and rename operations, file name tunneling can invalidate the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine. If a minifilter driver retrieves normalized file name information in a preoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>) routine by calling a routine such as <b>FltGetFileNameInformationUnsafe</b>, it must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a> from its postoperation callback (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>) routine to retrieve the correct file name information for the file. 

For more information about normalized file name information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544633">FLT_FILE_NAME_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544636">FLT_FILE_NAME_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543003">FltGetDestinationFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543032">FltGetFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543177">FltGetTunneledName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544301">FltReferenceFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544320">FltReleaseFileNameInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548608">IRP_MJ_CLEANUP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548405">IoGetTopLevelIrp</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551107">PFLT_POST_OPERATION_CALLBACK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551109">PFLT_PRE_OPERATION_CALLBACK</a>
 

 


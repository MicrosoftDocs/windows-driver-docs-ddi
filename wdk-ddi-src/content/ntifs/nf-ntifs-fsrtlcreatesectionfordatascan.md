---
UID: NF:ntifs.FsRtlCreateSectionForDataScan
title: FsRtlCreateSectionForDataScan function (ntifs.h)
description: The FsRtlCreateSectionForDataScan routine creates a section object.
old-location: ifsk\fsrtlcreatesectionfordatascan.htm
tech.root: ifsk
ms.assetid: 2bf6fb1b-e2d6-496d-808e-e739951cc7c5
ms.date: 04/16/2018
ms.keywords: FsRtlCreateSectionForDataScan, FsRtlCreateSectionForDataScan routine [Installable File System Drivers], fsrtlref_5117d865-19da-4ec5-8b20-cccab94eb013.xml, ifsk.fsrtlcreatesectionfordatascan, ntifs/FsRtlCreateSectionForDataScan
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCreateSectionForDataScan routine is available on Microsoft Windows Server 2003 SP1 and later, the Update Rollup for Windows 2000 Service Pack 4 (SP4), and the Filter Manager Rollup for Windows XP Service Pack 2 (SP2).
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlCreateSectionForDataScan
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlCreateSectionForDataScan function


## -description


The <b>FsRtlCreateSectionForDataScan</b> routine creates a section object. Use this routine with extreme caution. (See the following <i>Remarks</i> section.)


## -parameters




### -param SectionHandle [out]

Pointer to a caller-allocated variable that receives an opaque handle to the section object. 


### -param SectionObject [out]

Pointer to a caller-allocated variable that receives an opaque pointer to the section object.


### -param SectionFileSize [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the file at the time the section object was created. This parameter is optional and can be <b>NULL</b>.


### -param FileObject [in]

File object for an open file.  The section object will be backed by the specified file. This parameter is required and cannot be <b>NULL</b>.


### -param DesiredAccess [in]

Specifies the desired access for the section object as one or more of the following <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> flags. 

<table>
<tr>
<th><i>DesiredAccess</i> flag</th>
<th>Allows caller to </th>
</tr>
<tr>
<td>
SECTION_MAP_READ

</td>
<td>
Read views of the section.

</td>
</tr>
<tr>
<td>
SECTION_MAP_WRITE

</td>
<td>
Write views of the section.

</td>
</tr>
<tr>
<td>
SECTION_QUERY

</td>
<td>
Query the section object for information about the section. Drivers should set this flag.

</td>
</tr>
<tr>
<td>
SECTION_ALL_ACCESS

</td>
<td>
All actions defined by the previous flags as well as that defined by STANDARD_RIGHTS_REQUIRED. (For more information about STANDARD_RIGHTS_REQUIRED, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>.) 

</td>
</tr>
</table>
 


### -param ObjectAttributes [in, optional]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> macro to initialize this structure. Because <b>FsRtlCreateSectionForDataScan</b> inserts this object into the process handle table, the caller must specify the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


### -param MaximumSize [in, optional]

This parameter is reserved for future use.


### -param SectionPageProtection [in]

Specifies the protection to place on each page in the section. Specify one of the following values. This parameter is required and cannot be zero. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
PAGE_READONLY

</td>
<td>
Enables read-only access to the committed region of pages. An attempt to write to the committed region results in an access violation. If the system differentiates between read-only access and execute access, an attempt to execute code in the committed region results in an access violation.

</td>
</tr>
<tr>
<td>
PAGE_READWRITE

</td>
<td>
Enables both read and write access to the committed region of pages.

</td>
</tr>
</table>
 


### -param AllocationAttributes [in]

Bitmasks of the SEC_<i>XXX</i> flags determine the allocation attributes of the section. Specify one or more of the following values. This parameter is required and cannot be zero. 

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEC_COMMIT

</td>
<td>
Allocates physical storage in memory or in the paging file on disk for all pages of a section. This is the default setting. Note that this flag is required and cannot be omitted.

</td>
</tr>
<tr>
<td>
SEC_FILE

</td>
<td>
The file specified by the <i>FileObject</i> parameter is a mapped file.

</td>
</tr>
</table>
 


### -param Flags [in]

This parameter is reserved for future use.


## -returns



<b>FsRtlCreateSectionForDataScan</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_END_OF_FILE</b></dt>
</dl>
</td>
<td width="60%">
The size of the file specified by the FileObject parameter is zero. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
 
The file specified by the FileObject parameter is locked. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
 
FsRtlCreateSectionForDataScan encountered a pool allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_FILE_FOR_SECTION</b></dt>
</dl>
</td>
<td width="60%">
The file specified by the FileObject parameter does not support sections. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_8</b></dt>
</dl>
</td>
<td width="60%">
The value specified for the SectionPageProtection parameter is invalid. This is an error code. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b> 
STATUS_INVALID_PARAMETER_9</b></dt>
</dl>
</td>
<td width="60%">
 
The caller specified an invalid value for the AllocationAttributes parameter. This is an error code. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">

The caller did not have the required privilege to create a section object with the access specified in the DesiredAccess parameter. This is an error code. 

</td>
</tr>
</table>
 




## -remarks



<div class="alert"><b>Important</b>  The <b>FsRtlCreateSectionForDataScan</b> routine should only be used in cases where a handle to the file object specified in the <i>FileObject</i> parameter has not yet been created (typically while processing a post-create operation). If the driver has a handle to the file object or can obtain a handle to the file object, the driver should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566428">ZwCreateSection</a> routine instead.</div>
<div> </div>
Once the section object created by this routine is no longer necessary, be sure to close the section object's handle (<i>SectionHandle</i>) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> routine and dereference the section object itself (<i>SectionObject</i>) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557724">ObDereferenceObject</a> routine.

For more information on creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563684">Section Objects and Views</a>. Also see the documentation for the <b>CreateFileMapping</b> routine in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539188">CcPurgeCacheSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549808">MmFlushImageSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549811">MmForceSectionClosed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566428">ZwCreateSection</a>
 

 


---
UID: NF:ntifs.FsRtlCreateSectionForDataScan
title: FsRtlCreateSectionForDataScan function
author: windows-driver-content
description: The FsRtlCreateSectionForDataScan routine creates a section object.
old-location: ifsk\fsrtlcreatesectionfordatascan.htm
old-project: ifsk
ms.assetid: 2bf6fb1b-e2d6-496d-808e-e739951cc7c5
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlCreateSectionForDataScan
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCreateSectionForDataScan routine is available on Microsoft Windows Server 2003 SP1 and later, the Update Rollup for Windows 2000 Service Pack 4 (SP4), and the Filter Manager Rollup for Windows XP Service Pack 2 (SP2).
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCreateSectionForDataScan
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlCreateSectionForDataScan function



## -description
The <b>FsRtlCreateSectionForDataScan</b> routine creates a section object. Use this routine with extreme caution. (See the following <i>Remarks</i> section.)



## -syntax

````
NTSTATUS FsRtlCreateSectionForDataScan(
  _Out_     PHANDLE            SectionHandle,
  _Out_     PVOID              *SectionObject,
  _Out_opt_ PLARGE_INTEGER     SectionFileSize,
  _In_      PFILE_OBJECT       FileObject,
  _In_      ACCESS_MASK        DesiredAccess,
  _In_opt_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_  PLARGE_INTEGER     MaximumSize,
  _In_      ULONG              SectionPageProtection,
  _In_      ULONG              AllocationAttributes,
  _In_      ULONG              Flags
);
````


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

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> macro to initialize this structure. Because <b>FsRtlCreateSectionForDataScan</b> inserts this object into the process handle table, the caller must specify the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


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
<dl>
<dt><b>STATUS_END_OF_FILE</b></dt>
</dl>The size of the file specified by the FileObject parameter is zero. This is an error code.
<dl>
<dt><b> 
STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl> 
The file specified by the FileObject parameter is locked. This is an error code.
<dl>
<dt><b> 
STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl> 
FsRtlCreateSectionForDataScan encountered a pool allocation failure. This is an error code.
<dl>
<dt><b>STATUS_INVALID_FILE_FOR_SECTION</b></dt>
</dl>The file specified by the FileObject parameter does not support sections. This is an error code.
<dl>
<dt><b>STATUS_INVALID_PARAMETER_8</b></dt>
</dl>The value specified for the SectionPageProtection parameter is invalid. This is an error code. 

<dl>
<dt><b> 
STATUS_INVALID_PARAMETER_9</b></dt>
</dl> 
The caller specified an invalid value for the AllocationAttributes parameter. This is an error code. 

<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
The caller did not have the required privilege to create a section object with the access specified in the DesiredAccess parameter. This is an error code. 

 


## -remarks
Once the section object created by this routine is no longer necessary, be sure to close the section object's handle (<i>SectionHandle</i>) by calling the <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> routine and dereference the section object itself (<i>SectionObject</i>) by calling the <a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a> routine.

For more information on creating mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563684">Section Objects and Views</a>. Also see the documentation for the <b>CreateFileMapping</b> routine in the Microsoft Windows SDK. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccpurgecachesection.md">CcPurgeCacheSection</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-mmflushimagesection.md">MmFlushImageSection</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-mmforcesectionclosed.md">MmForceSectionClosed</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-zwcreatesection.md">ZwCreateSection</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCreateSectionForDataScan routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


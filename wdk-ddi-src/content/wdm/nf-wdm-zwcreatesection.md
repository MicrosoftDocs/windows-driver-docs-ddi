---
UID: NF:wdm.ZwCreateSection
title: ZwCreateSection function
author: windows-driver-content
description: The ZwCreateSection routine creates a section object.
old-location: kernel\zwcreatesection.htm
old-project: kernel
ms.assetid: 805d7eff-19be-47a1-acc9-1b97e5493031
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/NtCreateSection, ZwCreateSection routine [Kernel-Mode Driver Architecture], ZwCreateSection, NtCreateSection, wdm/ZwCreateSection, kernel.zwcreatesection, k111_8e0d13e2-4cd7-4b39-b1ce-41b193c495be.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwCreateSection
-	NtCreateSection
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwCreateSection function


## -description


The <b>ZwCreateSection</b> routine creates a <a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">section object</a>.


## -syntax


````
NTSTATUS ZwCreateSection(
  _Out_    PHANDLE            SectionHandle,
  _In_     ACCESS_MASK        DesiredAccess,
  _In_opt_ POBJECT_ATTRIBUTES ObjectAttributes,
  _In_opt_ PLARGE_INTEGER     MaximumSize,
  _In_     ULONG              SectionPageProtection,
  _In_     ULONG              AllocationAttributes,
  _In_opt_ HANDLE             FileHandle
);
````


## -parameters




### -param SectionHandle [out]

Pointer to a HANDLE variable that receives a handle to the section object.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>), the caller can specify any of the following access rights, which are specific to section objects:

<table>
<tr>
<th><i>DesiredAccess</i> flag</th>
<th>Allows caller to do this</th>
</tr>
<tr>
<td>
SECTION_EXTEND_SIZE

</td>
<td>
Dynamically extend the size of the section.

</td>
</tr>
<tr>
<td>
SECTION_MAP_EXECUTE

</td>
<td>
Execute views of the section.

</td>
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
All of the previous flags combined with STANDARD_RIGHTS_REQUIRED.

</td>
</tr>
</table>
 


### -param ObjectAttributes [in, optional]

Pointer to an <a href="..\wudfwdm\ns-wudfwdm-_object_attributes.md">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.


### -param MaximumSize [in, optional]

Specifies the maximum size, in bytes, of the section. <b>ZwCreateSection</b> rounds this value up to the nearest multiple of PAGE_SIZE. If the section is backed by the paging file, <i>MaximumSize</i> specifies the actual size of the section. If the section is backed by an ordinary file, <i>MaximumSize</i> specifies the maximum size that the file can be extended or mapped to.


### -param SectionPageProtection [in]

Specifies the protection to place on each page in the section. Use one of the following four values: PAGE_READONLY, PAGE_READWRITE, PAGE_EXECUTE, or PAGE_WRITECOPY. For a description of these values, see <a href="https://msdn.microsoft.com/d3302183-76a0-47ec-874f-1173db353dfe">CreateFileMapping</a>.


### -param AllocationAttributes [in]

Specifies a bitmask of SEC_<i>XXX</i> flags that determines the allocation attributes of the section. For a description of these flags, see <a href="https://msdn.microsoft.com/d3302183-76a0-47ec-874f-1173db353dfe">CreateFileMapping</a>.


### -param FileHandle [in, optional]

Optionally specifies a handle for an open file object. If the value of <i>FileHandle</i> is <b>NULL</b>, the section is backed by the paging file. Otherwise, the section is backed by the specified file. 


## -returns



<b>ZwCreateSection</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
The file specified by the <i>FileHandle</i> parameter is locked.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_FILE_FOR_SECTION</b></dt>
</dl>
</td>
<td width="60%">
The file specified by <i>FileHandle</i> does not support sections.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PAGE_PROTECTION</b></dt>
</dl>
</td>
<td width="60%">
The value specified for the <i>SectionPageProtection</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MAPPED_FILE_SIZE_ZERO</b></dt>
</dl>
</td>
<td width="60%">
The size of the file specified by <i>FileHandle</i> is zero, and <i>MaximumSize</i> is zero.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SECTION_TOO_BIG</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>MaximumSize</i> is too big. This occurs when either <i>MaximumSize</i> is greater than the system-defined maximum for sections, or if <i>MaximumSize</i> is greater than the specified file and the section is not writable.

</td>
</tr>
</table>
 




## -remarks



Once the handle pointed to by <i>SectionHandle</i> is no longer in use, the driver must call <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>. 

For more information about setting up mapped sections and views of memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563682">Sections and Views</a>. 

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateSection</b>" instead of "<b>ZwCreateSection</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwopensection.md">ZwOpenSection</a>



<a href="..\wdm\nf-wdm-zwunmapviewofsection.md">ZwUnmapViewOfSection</a>



<a href="https://msdn.microsoft.com/d3302183-76a0-47ec-874f-1173db353dfe">CreateFileMapping</a>



<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>



<a href="..\wdm\nf-wdm-zwmapviewofsection.md">ZwMapViewOfSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwCreateSection routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


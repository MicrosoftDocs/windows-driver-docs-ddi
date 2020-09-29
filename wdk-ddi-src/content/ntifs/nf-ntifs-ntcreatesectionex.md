---
UID: NF:ntifs.NtCreateSectionEx
title: NtCreateSectionEx function (ntifs.h)
description: Creates a section object.
ms.assetid: a895e706-38c0-40d7-95b1-f1268af775c1
tech.root: kernel
ms.date: 10/19/2018
keywords: ["NtCreateSectionEx function"]
ms.keywords: NtCreateSectionEx
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - NtCreateSectionEx
 - ntifs/NtCreateSectionEx
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - NtCreateSectionEx
dev_langs:
 - c++
---

# NtCreateSectionEx function


## -description

An extended version of [**NtCreateSection**](nf-ntifs-ntcreatesection.md) that creates a section object by specifying to indicate that this is actually an AWE section.

## -parameters

### -param SectionHandle

[out] Pointer to a HANDLE variable that receives a handle to the section object.

### -param DesiredAccess 

[out] 
Specifies an <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the object. In addition to the access rights that are defined for all types of objects (see <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>), the caller can specify any of the following access rights, which are specific to section objects:


|DesiredAccess flag|Allows caller to do this|
|---|---|
|SECTION_EXTEND_SIZE|Dynamically extend the size of the section.|
|SECTION_MAP_EXECUTE|Execute views of the section.|
|SECTION_MAP_READ|Read views of the section.|
|SECTION_MAP_WRITE|Write views of the section.|
|SECTION_QUERY|Query the section object for information about the section. Drivers should set this flag.|
|SECTION_ALL_ACCESS|All of the previous flags combined with STANDARD_RIGHTS_REQUIRED.|

### -param ObjectAttributes 

[in, optional]
Pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>.

### -param MaximumSize 

[in, optional]
Specifies the maximum size, in bytes, of the section. <b>NtCreateSection</b> rounds this value up to the nearest multiple of PAGE_SIZE. If the section is backed by the paging file, <i>MaximumSize</i> specifies the actual size of the section. If the section is backed by an ordinary file, <i>MaximumSize</i> specifies the maximum size that the file can be extended or mapped to.

### -param SectionPageProtection 

[in]
Specifies the protection to place on each page in the section. Use one of the following four values: PAGE_READONLY, PAGE_READWRITE, PAGE_EXECUTE, or PAGE_WRITECOPY. For a description of these values, see <a href="/windows/win32/api/winbase/nf-winbase-createfilemappinga">CreateFileMapping</a>.

### -param AllocationAttributes 

[in]
Specifies a bitmask of SEC_<i>XXX</i> flags that determines the allocation attributes of the section. For a description of these flags, see <a href="/windows/win32/api/winbase/nf-winbase-createfilemappinga">CreateFileMapping</a>.

### -param FileHandle 

[in, optional]
Optionally specifies a handle for an open file object. If the value of <i>FileHandle</i> is <b>NULL</b>, the section is backed by the paging file. Otherwise, the section is backed by the specified file.

### -param ExtendedParameters 

[in/out]A pointer to an array of [**MEM_EXTENDED_PARAMETER**](../wdm/ns-wdm-mem_extended_parameter.md) structures the contains the extended paramters to create the section.

### -param ExtendedParameterCount

The size of the _ExtendedParameters_ array.

## -returns

eturns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure. Possible error status codes include the following:

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

Once the handle pointed to by <i>SectionHandle</i> is no longer in use, the driver must call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">NtClose</a> to close it.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="/windows-hardware/drivers/kernel/object-handles">Object Handles</a>. 

For more information about setting up mapped sections and views of memory, see <a href="/windows-hardware/drivers/ddi/index">Sections and Views</a>. 

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtCreateSection</b>" instead of "<b>ZwCreateSection</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.


stack-based extended parameter if preferred NUMA node was specified.

Only one instance of an extended parameter can be specified.

Convert to a 1-based numa node number that is expected downstream of this API.

## -see-also
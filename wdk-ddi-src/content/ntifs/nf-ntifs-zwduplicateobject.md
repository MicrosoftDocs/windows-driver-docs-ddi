---
UID: NF:ntifs.ZwDuplicateObject
title: ZwDuplicateObject function (ntifs.h)
description: The ZwDuplicateObject routine creates a handle that is a duplicate of the specified source handle.
old-location: kernel\zwduplicateobject.htm
tech.root: kernel
ms.assetid: 9a922379-b439-4f94-9eb1-7c229318382c
ms.date: 04/30/2018
keywords: ["ZwDuplicateObject function"]
ms.keywords: NtDuplicateObject, ZwDuplicateObject, ZwDuplicateObject routine [Kernel-Mode Driver Architecture], kernel.zwduplicateobject, ntifs/NtDuplicateObject, ntifs/ZwDuplicateObject
req.header: ntifs.h
req.include-header: Ntdef.h, Ntifs.h, Fltkernel.h
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
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwDuplicateObject
 - ntifs/ZwDuplicateObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ntoskrnl.lib
 - ntoskrnl.dll
api_name:
 - ZwDuplicateObject
 - NtDuplicateObject
---

# ZwDuplicateObject function


## -description

The <b>ZwDuplicateObject</b> routine creates a handle that is a duplicate of the specified source handle.

## -parameters

### -param SourceProcessHandle 

[in]
A handle to the source process for the handle being duplicated.

### -param SourceHandle 

[in]
The handle to duplicate.

### -param TargetProcessHandle 

[in, optional]
A handle to the target process that is to receive the new handle. This parameter is optional and can be specified as NULL if the <b>DUPLICATE_CLOSE_SOURCE</b> flag is set in <i>Options</i>.

### -param TargetHandle 

[out, optional]
A pointer to a HANDLE variable into which the routine writes the new duplicated handle. The duplicated handle is valid in the specified target process. This parameter is optional and can be specified as NULL if no duplicate handle is to be created.

### -param DesiredAccess 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the desired access for the new handle.

### -param HandleAttributes 

[in]
A ULONG that specifies the desired attributes for the new handle. For more information about attributes, see the description of the <b>Attributes</b> member in <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>.

### -param Options 

[in]
A set of flags to control the behavior of the duplication operation. Set this parameter to zero or to the bitwise OR of one or more of the following flags.

<table>
<tr>
<th>Flag name</th>
<th>Description</th>
</tr>
<tr>
<td><b>DUPLICATE_SAME_ATTRIBUTES</b></td>
<td>Instead of using the <i>HandleAttributes</i> parameter, copy the attributes from the source handle to the target handle.</td>
</tr>
<tr>
<td><b>DUPLICATE_SAME_ACCESS</b></td>
<td>Instead of using the <i>DesiredAccess</i> parameter, copy the access rights from the source handle to the target handle.</td>
</tr>
<tr>
<td><b>DUPLICATE_CLOSE_SOURCE</b></td>
<td>Close the source handle.</td>
</tr>
</table>

## -returns

<b>ZwDuplicateObject</b> returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.

## -remarks

The source handle is evaluated in the context of the specified source process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the source process. The duplicate handle is created in the handle table of the specified target process. The calling process must have <b>PROCESS_DUP_HANDLE</b> access to the target process.

By default, the duplicate handle is created with the attributes specified by the <i>HandleAttributes</i> parameter, and with the access rights specified by the <i>DesiredAccess</i> parameter. If necessary, the caller can override one or both defaults by setting the <b>DUPLICATE_SAME_ATTRIBUTES</b> and <b>DUPLICATE_SAME_ACCESS</b> flags in the <i>Options</i> parameter.

If the call to this function occurs in user mode, you should use the name "<b>NtDuplicateObject</b>" instead of "<b>ZwDuplicateObject</b>".

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>


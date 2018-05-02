---
UID: NF:wdm.NtQueryInformationResourceManager
title: NtQueryInformationResourceManager function
author: windows-driver-content
description: The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object.
old-location: kernel\zwqueryinformationresourcemanager.htm
old-project: kernel
ms.assetid: 6faeb410-486e-4b79-b942-62d16039d24b
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtQueryInformationResourceManager, ZwQueryInformationResourceManager, ZwQueryInformationResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwqueryinformationresourcemanager, ktm_ref_2232fa2b-badb-4054-8a99-65f55ca1bff5.xml, wdm/NtQueryInformationResourceManager, wdm/ZwQueryInformationResourceManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later operating system versions.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ZwQueryInformationResourceManager
-	NtQueryInformationResourceManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtQueryInformationResourceManager function


## -description


The <b>ZwQueryInformationResourceManager</b> routine retrieves information about a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -parameters




### -param ResourceManagerHandle [in]

A handle to a resource manager object that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object.


### -param ResourceManagerInformationClass [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561090">RESOURCEMANAGER_INFORMATION_CLASS</a>-typed value that specifies the information to retrieve. This value must be <b>ResourceManagerBasicInformation</b>.


### -param ResourceManagerInformation [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561084">RESOURCEMANAGER_BASIC_INFORMATION</a> structure that receives information from <b>ZwQueryInformationResourceManager</b>.


### -param ResourceManagerInformationLength [in]

The length, in bytes, of the buffer that the <i>ResourceManagerInformation</i> parameter points to.


### -param ReturnLength [out, optional]

A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>ResourceManagerInformation</i> buffer. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwQueryInformationResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The specified handle is not a handle to a resource manager object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
An object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
The <i>ResourceManagerInformationClass</i> parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size that the <i>ResourceManagerInformationLength </i>parameter specifies is smaller than the RESOURCEMANAGER_BASIC_INFORMATION structure.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The buffer size that the <i>ResourceManagerInformationLength </i>parameter specifies is too small to receive all the variable-length information that is available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the resource manager object.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



For more information about the <b>ZwQueryInformationResourceManager</b> routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff542865">Creating a Resource Manager</a>.

<b>NtQueryInformationResourceManager</b> and <b>ZwQueryInformationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561084">RESOURCEMANAGER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561090">RESOURCEMANAGER_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567078">ZwRecoverResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567098">ZwSetInformationResourceManager</a>
 

 


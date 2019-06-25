---
UID: NF:wdm.ZwQueryInformationResourceManager
title: ZwQueryInformationResourceManager function (wdm.h)
description: The ZwQueryInformationResourceManager routine retrieves information about a specified resource manager object.
old-location: kernel\zwqueryinformationresourcemanager.htm
tech.root: kernel
ms.assetid: 6faeb410-486e-4b79-b942-62d16039d24b
ms.date: 04/30/2018
ms.keywords: NtQueryInformationResourceManager, ZwQueryInformationResourceManager, ZwQueryInformationResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwqueryinformationresourcemanager, ktm_ref_2232fa2b-badb-4054-8a99-65f55ca1bff5.xml, wdm/NtQueryInformationResourceManager, wdm/ZwQueryInformationResourceManager
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwQueryInformationResourceManager
- NtQueryInformationResourceManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwQueryInformationResourceManager function


## -description


The <b>ZwQueryInformationResourceManager</b> routine retrieves information about a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a>.


## -parameters




### -param ResourceManagerHandle [in]

A handle to a resource manager object that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_QUERY_INFORMATION access to the object.


### -param ResourceManagerInformationClass [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_resourcemanager_information_class">RESOURCEMANAGER_INFORMATION_CLASS</a>-typed value that specifies the information to retrieve. This value must be <b>ResourceManagerBasicInformation</b>.


### -param ResourceManagerInformation [out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a> structure that receives information from <b>ZwQueryInformationResourceManager</b>.


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
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



For more information about the <b>ZwQueryInformationResourceManager</b> routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>.

<b>NtQueryInformationResourceManager</b> and <b>ZwQueryInformationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_resourcemanager_basic_information">RESOURCEMANAGER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_resourcemanager_information_class">RESOURCEMANAGER_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntrecoverresourcemanager">ZwRecoverResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ntsetinformationresourcemanager">ZwSetInformationResourceManager</a>
 

 


---
UID: NF:wdm.NtOpenEnlistment
title: NtOpenEnlistment function (wdm.h)
description: The ZwOpenEnlistment routine obtains a handle to an existing enlistment object.
old-location: kernel\zwopenenlistment.htm
tech.root: kernel
ms.assetid: b70d524f-2341-4b19-9c4a-f5095cb7f412
ms.date: 04/30/2018
keywords: ["NtOpenEnlistment function"]
ms.keywords: NtOpenEnlistment, ZwOpenEnlistment, ZwOpenEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwopenenlistment, ktm_ref_cc7719f5-a9a2-42be-9961-01f910f864bc.xml, wdm/NtOpenEnlistment, wdm/ZwOpenEnlistment
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - NtOpenEnlistment
 - wdm/NtOpenEnlistment
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenEnlistment
 - NtOpenEnlistment
---

# NtOpenEnlistment function


## -description

The <b>ZwOpenEnlistment</b> routine obtains a handle to an existing <a href="/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.

## -parameters

### -param EnlistmentHandle 

[out]
A pointer to a caller-allocated variable that receives a handle to an enlistment object if the call to <b>ZwOpenEnlistment</b> succeeds.

### -param DesiredAccess 

[in]
An <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>-typed value that specifies the requested access to the enlistment object. For more information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>. This parameter cannot be zero.

### -param ResourceManagerHandle 

[in]
A handle to a resource manager object that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>.

### -param EnlistmentGuid 

[in]
A pointer to a GUID that identifies the enlistment. For more information, see the following Remarks section.

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>ZwOpenEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The object handle is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the enlistment object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DesiredAccess</i> parameter's value is zero, or the <i>EnlistmentGuid</i> parameter's value is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ENLISTMENT_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The enlistment that the <i>EnlistmentGuid</i> parameter specifies does not exist for the resource manager that the <i>RmHandle </i>parameter specifies.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>DesiredAccess</i> parameter is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

Typically, a TPS component calls <b>ZwOpenEnlistment</b> after it receives an enlistment GUID from another TPS component that had previously called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>. Most TPS designs do not require calling <b>ZwOpenEnlistment</b>.

A resource manager that calls <b>ZwOpenEnlistment</b> must eventually call <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close the object handle.

For more information about <b>ZwOpenEnlistment</b>, see <a href="/windows-hardware/drivers/kernel/enlistment-objects">Enlistment Objects</a>.

<b>NtOpenEnlistment</b> and <b>ZwOpenEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows/win32/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>
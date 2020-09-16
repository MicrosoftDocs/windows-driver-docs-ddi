---
UID: NF:wdm.NtOpenResourceManager
title: NtOpenResourceManager function (wdm.h)
description: The ZwOpenResourceManager routine returns a handle to an existing resource manager object.
old-location: kernel\zwopenresourcemanager.htm
tech.root: kernel
ms.assetid: baa12e3c-dc17-4fef-bce4-29c50328314c
ms.date: 04/30/2018
keywords: ["NtOpenResourceManager function"]
ms.keywords: NtOpenResourceManager, ZwOpenResourceManager, ZwOpenResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwopenresourcemanager, ktm_ref_f873ba66-20d0-4498-a8b6-d62bf8593d05.xml, wdm/NtOpenResourceManager, wdm/ZwOpenResourceManager
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
 - NtOpenResourceManager
 - wdm/NtOpenResourceManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwOpenResourceManager
 - NtOpenResourceManager
---

# NtOpenResourceManager function


## -description

The <b>ZwOpenResourceManager</b> routine returns a handle to an existing <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a>.

## -parameters

### -param ResourceManagerHandle 

[out]
A pointer to a caller-allocated variable that receives the resource manager handle if the call to <b>ZwOpenResourceManager</b> succeeds.

### -param DesiredAccess 

[in]
An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the caller's requested access to the resource manager object. For more information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>. This parameter cannot be zero.

### -param TmHandle 

[in]
A handle to a transaction manager object that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransactionmanager">ZwOpenTransactionManager</a>.

### -param ResourceManagerGuid 

[in]
A pointer to the GUID that identifies the resource manager to open.

### -param ObjectAttributes 

[in, optional]
A pointer to an <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object's attributes. Use the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure, but specify only that routine's <i>InitializedAttributes</i> and <i>Attributes</i> parameters. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE flag in the <i>Attributes</i> parameter. This parameter is optional and can be <b>NULL</b>.

## -returns

<b>ZwOpenResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The handle that <i>TmHandle</i> specifies is not a handle to a transaction object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The handle that <i>TmHandle</i> specifies is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the specified transaction manager object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>DesiredAccess</i> parameter is zero or the <i>ResourceManagerGuid</i> parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_RESOURCEMANAGER_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The specified resource manager could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>
</td>
<td width="60%">
The specified transaction manager is not online.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

Typically, a TPS component calls <b>ZwOpenResourceManager</b> after it receives an enlistment GUID from another TPS component that had previously called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>. Most TPS designs do not require calling <b>ZwOpenResourceManager</b>.

A resource manager that calls <b>ZwOpenResourceManager</b> must eventually call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close the object handle.

For more information about <b>ZwOpenResourceManager</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ktm-objects">KTM Objects</a>.

<b>NtOpenResourceManager</b> and <b>ZwOpenResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransactionmanager">ZwOpenTransactionManager</a>


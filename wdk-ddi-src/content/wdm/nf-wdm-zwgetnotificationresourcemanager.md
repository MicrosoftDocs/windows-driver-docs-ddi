---
UID: NF:wdm.ZwGetNotificationResourceManager
title: ZwGetNotificationResourceManager function (wdm.h)
description: The ZwGetNotificationResourceManager routine retrieves the next transaction notification from a specified resource manager's notification queue.
old-location: kernel\zwgetnotificationresourcemanager.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwGetNotificationResourceManager function"]
ms.keywords: NtGetNotificationResourceManager, ZwGetNotificationResourceManager, ZwGetNotificationResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwgetnotificationresourcemanager, ktm_ref_c0a3b128-d49c-4080-ae12-0081ab5a27e9.xml, wdm/NtGetNotificationResourceManager, wdm/ZwGetNotificationResourceManager
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
req.irql: = PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwGetNotificationResourceManager
 - wdm/ZwGetNotificationResourceManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwGetNotificationResourceManager
 - NtGetNotificationResourceManager
---

# ZwGetNotificationResourceManager function


## -description

The <b>ZwGetNotificationResourceManager</b> routine retrieves the next <a href="/windows-hardware/drivers/kernel/transaction-notifications">transaction notification</a> from a specified resource manager's notification queue.

## -parameters

### -param ResourceManagerHandle 

[in]
A handle to a <a href="/windows-hardware/drivers/kernel/resource-manager-objects">resource manager object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_GET_NOTIFICATION access to the object.

### -param TransactionNotification 

[out]
A pointer to a caller-allocated buffer that receives information about the retrieved notification. The buffer must be large enough to contain a <a href="/previous-versions/windows/hardware/drivers/ff564813(v=vs.85)">TRANSACTION_NOTIFICATION</a> structure plus additional notification-specific arguments.

### -param NotificationLength 

[in]
The length, in bytes, of the buffer that the <i>TransactionNotification </i>parameter points to.

### -param Timeout 

[in]
A pointer to a value that specifies a relative or absolute time, in units of 100 nanoseconds. This pointer is optional and can be <b>NULL</b>.

If the pointer is <b>NULL</b>, <b>ZwGetNotificationResourceManager</b> does not return until a transaction notification is available. If a time value is specified, <b>ZwGetNotificationResourceManager</b> returns when a notification is available or after the specified time elapses, whichever comes first.

A negative value specifies a time that is relative to the current system time. For example, a relative time value of five seconds causes <b>ZwGetNotificationResourceManager</b> to time out five seconds after it is called. 

A positive value specifies an absolute time, which is actually relative to 00:00, January 1, 1601. If an absolute time value is specified, the operating system adds the absolute time value to the time value that represents 00:00, January 1, 1601.

If the caller specifies a zero value (instead of a <b>NULL</b> pointer), <b>ZwGetNotificationResourceManager</b> returns immediately, whether a notification is available or not.

### -param ReturnLength 

[out, optional]
An optional pointer to a variable. If this pointer is not <b>NULL</b>, and if the <i>NotificationLength</i> parameter's value is too small, <b>ZwGetNotificationResourceManager</b> supplies the required length in the variable and returns STATUS_BUFFER_TOO_SMALL.

### -param Asynchronous 

[in]
A ULONG value that must be zero. <b>ZwGetNotificationResourceManager</b> does not support asynchronous notifications. Use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmenablecallbacks">TmEnableCallbacks</a> to enable asynchronous notifications.

### -param AsynchronousContext 

[in, optional]
A pointer to a ULONG value. This pointer must be <b>NULL</b>.

## -returns

<b>ZwGetNotificationResourceManager</b> returns STATUS_SUCCESS if the operation succeeds and a notification is available. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TIMEOUT</b></dt>
</dl>
</td>
<td width="60%">
The time-out interval that <i>Timeout</i> specifies elapsed before a notification became available.

</td>
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
The caller does not have appropriate access to the resource manager object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The <i>NotificationLength</i> parameter's value is too small.

</td>
</tr>
</table>
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

Use the <b>ZwGetNotificationResourceManager</b> routine to obtain notifications synchronously. Use the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmenablecallbacks">TmEnableCallbacks</a> routine to enable asynchronous notifications. 

The received <a href="/previous-versions/windows/hardware/drivers/ff564813(v=vs.85)">TRANSACTION_NOTIFICATION</a> structure contains the enlistment key that the resource manager specified when it called <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>. You can use the enlistment key to identify the enlistment that the notification applies to.

For more information about the <b>ZwGetNotificationResourceManager</b> routine, see <a href="/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>. 

<b>NtGetNotificationResourceManager</b> and <b>ZwGetNotificationResourceManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/previous-versions/windows/hardware/drivers/ff564813(v=vs.85)">TRANSACTION_NOTIFICATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmenablecallbacks">TmEnableCallbacks</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateresourcemanager">ZwCreateResourceManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenresourcemanager">ZwOpenResourceManager</a>

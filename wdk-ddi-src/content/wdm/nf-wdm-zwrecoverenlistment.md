---
UID: NF:wdm.ZwRecoverEnlistment
title: ZwRecoverEnlistment function
author: windows-driver-content
description: The ZwRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment.
old-location: kernel\zwrecoverenlistment.htm
old-project: kernel
ms.assetid: 0f34d2d1-bb3a-4529-9ced-d9bed998c4ce
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/NtRecoverEnlistment, ktm_ref_0a6564fb-c6d1-4b4b-a278-a1d78395c1b4.xml, NtRecoverEnlistment, ZwRecoverEnlistment routine [Kernel-Mode Driver Architecture], ZwRecoverEnlistment, kernel.zwrecoverenlistment, wdm/ZwRecoverEnlistment
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwRecoverEnlistment
-	NtRecoverEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwRecoverEnlistment function


## -description


The <b>ZwRecoverEnlistment</b> routine initiates a recovery operation for the transaction that is associated with a specified enlistment.


## -syntax


````
NTSTATUS ZwRecoverEnlistment(
  _In_     HANDLE EnlistmentHandle,
  _In_opt_ PVOID  EnlistmentKey
);
````


## -parameters




### -param EnlistmentHandle [in]

A handle to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_RECOVER access to the object.


### -param EnlistmentKey [in, optional]

A pointer to the enlistment key value that the resource manager previously specified as the <i>EnlistmentKey</i> parameter to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>. This parameter is optional and can be <b>NULL</b> if the resource manager did not provide an enlistment key when it called <b>ZwCreateEnlistment</b>. 


## -returns



<b>ZwRecoverEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The specified handle is not a handle to an enlistment object.

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
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
KTM has added a commit, rollback, or in-doubt notification to the resource manager's notification queue, and the resource manager is not using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine.

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
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



After a resource manager calls <b>ZwRecoverEnlistment</b>, KTM delivers either a TRANSACTION_NOTIFY_COMMIT, TRANSACTION_NOTIFY_ROLLBACK, or TRANSACTION_NOTIFY_INDOUBT <a href="https://msdn.microsoft.com/62169b56-e70f-4d32-a051-a7fd947dbc64">notification</a> for the enlistment. Therefore, unless the resource manager is using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine, it must immediately call <a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a> if <b>ZwRecoverEnlistment</b> returns STATUS_SUCCESS or STATUS_PENDING. 

For more information about <b>ZwRecoverEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

<b>NtRecoverEnlistment</b> and <b>ZwRecoverEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="..\wdm\nf-wdm-tmrecoverenlistment.md">TmRecoverEnlistment</a>



<a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a>



<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwRecoverEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


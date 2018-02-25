---
UID: NF:wdm.TmRecoverEnlistment
title: TmRecoverEnlistment function
author: windows-driver-content
description: The TmRecoverEnlistment routine initiates a recovery operation for the transaction that is associated with a specified enlistment.
old-location: kernel\tmrecoverenlistment.htm
old-project: kernel
ms.assetid: 2483ca0e-f9b5-4cd0-a5c5-29b48099d86f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , E, R, T, TmRecoverEnlistment, TmRecoverEnlistment routine [Kernel-Mode Driver Architecture], c, e, i, kernel.tmrecoverenlistment, ktm_ref_bcbfbdfe-017c-4d33-a0f5-dda597ee9166.xml, l, m, n, o, r, s, t, v, wdm/TmRecoverEnlistment"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname:
-	TmRecoverEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmRecoverEnlistment function


## -description


The <b>TmRecoverEnlistment</b> routine initiates a recovery operation for the transaction that is associated with a specified enlistment.


## -syntax


````
NTSTATUS TmRecoverEnlistment(
  _In_ PKENLISTMENT Enlistment,
  _In_ PVOID        EnlistmentKey
);
````


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.


### -param EnlistmentKey [in]

A pointer to the enlistment key value that the resource manager previously specified as the <i>EnlistmentKey</i> parameter to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>. This parameter is optional and can be <b>NULL</b> if the resource manager did not provide an enlistment key when it called <b>ZwCreateEnlistment</b> or <b>TmCreateEnlistment</b>.


## -returns



<b>TmRecoverEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
An object handle is invalid.

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
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmRecoverEnlistment</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwrecoverenlistment.md">ZwRecoverEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.

For more information about recovery operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564813">TRANSACTION_NOTIFICATION</a>



<a href="..\wdm\nf-wdm-zwgetnotificationresourcemanager.md">ZwGetNotificationResourceManager</a>



<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="..\wdm\nf-wdm-zwrecoverenlistment.md">ZwRecoverEnlistment</a>



<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmRecoverEnlistment routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


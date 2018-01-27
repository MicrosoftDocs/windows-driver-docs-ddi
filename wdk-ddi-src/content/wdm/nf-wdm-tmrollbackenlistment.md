---
UID: NF:wdm.TmRollbackEnlistment
title: TmRollbackEnlistment function
author: windows-driver-content
description: The TmRollbackEnlistment routine rolls back a specified enlistment.
old-location: kernel\tmrollbackenlistment.htm
old-project: kernel
ms.assetid: 1f089f2c-73e2-4c77-a398-0d369aafdf3a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.tmrollbackenlistment, TmRollbackEnlistment, wdm/TmRollbackEnlistment, TmRollbackEnlistment routine [Kernel-Mode Driver Architecture], ktm_ref_adca7b83-77e1-4c1d-9ed8-aac2c713d43c.xml
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
-	TmRollbackEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmRollbackEnlistment function


## -description


The <b>TmRollbackEnlistment</b> routine rolls back a specified enlistment.


## -syntax


````
NTSTATUS TmRollbackEnlistment(
  _In_ PKENLISTMENT   Enlistment,
  _In_ PLARGE_INTEGER TmVirtualClock
);
````


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>, <a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>, or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns


<b>TmRollbackEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The enlistment cannot be rolled back.

</td>
</tr>
</table> 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



## -remarks


The <b>TmRollbackEnlistment</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwrollbackenlistment.md">ZwRollbackEnlistment</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\wdm\nf-wdm-zwrollbackenlistment.md">ZwRollbackEnlistment</a>

<a href="..\wdm\nf-wdm-tmcreateenlistment.md">TmCreateEnlistment</a>

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>

<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmRollbackEnlistment routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


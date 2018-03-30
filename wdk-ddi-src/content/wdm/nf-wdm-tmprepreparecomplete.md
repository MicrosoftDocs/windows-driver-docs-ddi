---
UID: NF:wdm.TmPrePrepareComplete
title: TmPrePrepareComplete function
author: windows-driver-content
description: The TmPrePrepareComplete routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data.
old-location: kernel\tmprepreparecomplete.htm
old-project: kernel
ms.assetid: 2152e174-c02e-425c-a969-83656052078b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: TmPrePrepareComplete, TmPrePrepareComplete routine [Kernel-Mode Driver Architecture], kernel.tmprepreparecomplete, ktm_ref_8ea6e6df-93c0-4b25-9bfe-3d53fbe1793f.xml, wdm/TmPrePrepareComplete
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmPrePrepareComplete
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmPrePrepareComplete function


## -description


The <b>TmPrePrepareComplete</b> routine notifies KTM that the calling resource manager has finished preliminary preparation of a transaction's data.


## -parameters




### -param Enlistment [in]

A pointer to an <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>. Your component can receive this pointer as input to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a> callback routine. Alternatively, your component can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a> provided.


### -param TmVirtualClock [in]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>TmPrePrepareComplete</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_NOT_REQUESTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state. For example, KTM did not send a TRANSACTION_NOTIFY_PREPARE notification.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmPrePrepareComplete</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567040">ZwPrePrepareComplete</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561077">ResourceManagerNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564669">TmCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566422">ZwCreateEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567008">ZwOpenEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567040">ZwPrePrepareComplete</a>
 

 


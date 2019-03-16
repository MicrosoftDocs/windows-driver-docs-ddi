---
UID: NF:wdm.TmRollbackTransaction
title: TmRollbackTransaction function (wdm.h)
description: The TmRollbackTransaction routine initiates a rollback operation for a specified transaction.
old-location: kernel\tmrollbacktransaction.htm
tech.root: kernel
ms.assetid: 5626a92e-bd26-41a3-8475-916efb2292ff
ms.date: 04/30/2018
ms.keywords: TmRollbackTransaction, TmRollbackTransaction routine [Kernel-Mode Driver Architecture], kernel.tmrollbacktransaction, ktm_ref_5ea93853-7ca0-4db2-b5ca-3329b5c7f0f0.xml, wdm/TmRollbackTransaction
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ext-MS-Win-ntos-tm-l1-1-0.dll
- tm.sys
api_name:
- TmRollbackTransaction
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmRollbackTransaction function


## -description


The <b>TmRollbackTransaction</b> routine initiates a rollback operation for a specified transaction.


## -parameters




### -param Transaction [in]

A pointer to a <a href="https://msdn.microsoft.com/124105bd-70be-49b1-8ea4-af6ba1f3cf16">transaction object</a>. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a> provided.


### -param Wait [in]

A Boolean value that the caller sets to <b>TRUE</b> for synchronous operation or <b>FALSE</b> for asynchronous operation. If this parameter is set to <b>TRUE</b>, the call does not return until the rollback operation is complete.


## -returns



<b>TmRollbackTransaction</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_ALREADY_COMMITTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction cannot be rolled back because it has already been committed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTION_REQUEST_NOT_VALID</b></dt>
</dl>
</td>
<td width="60%">
The transaction has not been committed but its current state does not permit rollback.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
Rollback notifications have been queued to resource managers, and the caller specified <b>FALSE</b> for the <i>Wait</i> parameter.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmRollbackTransaction</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567086">ZwRollbackTransaction</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566429">ZwCreateTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567033">ZwOpenTransaction</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567086">ZwRollbackTransaction</a>
 

 


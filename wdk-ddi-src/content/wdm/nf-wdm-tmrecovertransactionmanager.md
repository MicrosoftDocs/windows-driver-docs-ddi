---
UID: NF:wdm.TmRecoverTransactionManager
title: TmRecoverTransactionManager function (wdm.h)
description: The TmRecoverTransactionManager routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.
old-location: kernel\tmrecovertransactionmanager.htm
tech.root: kernel
ms.assetid: 67b18170-a17f-44fd-a5ab-12bccf2082fe
ms.date: 04/30/2018
ms.keywords: TmRecoverTransactionManager, TmRecoverTransactionManager routine [Kernel-Mode Driver Architecture], kernel.tmrecovertransactionmanager, ktm_ref_1917a36a-c7bd-4a00-b054-bb710b7c0e93.xml, wdm/TmRecoverTransactionManager
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
-	TmRecoverTransactionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmRecoverTransactionManager function


## -description


The <b>TmRecoverTransactionManager</b> routine reconstructs the state of the transaction manager object (including all transactions, enlistments, and resource managers) from the recovery information that is in the log stream.


## -parameters




### -param Tm [in]

A pointer to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a>. To obtain this pointer, your TPS component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566430">ZwCreateTransactionManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567035">ZwOpenTransactionManager</a> provided.


### -param TargetVirtualClock [in]

A pointer to a <a href="https://msdn.microsoft.com/de01b0f1-86b1-4e7d-af22-84dbbe3a3f83">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section. For Windows Vista, this parameter must be <b>NULL</b>.


## -returns



<b>TmRecoverTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
For Windows Vista, the caller specified a non-<b>NULL</b> value for the <i>TargetVirtualClock</i> parameter. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TM_VOLATILE</b></dt>
</dl>
</td>
<td width="60%">
The specified transaction manager object does not have a log file, so recovery is not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified transaction manager object is in an unexpected state.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmRecoverTransactionManager</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567079">ZwRecoverTransactionManager</a> routine.

Calling <b>TmRecoverTransactionManager</b> with a <i>TargetVirtualClock</i> parameter value of <b>NULL</b> is functionally equivalent to calling <b>ZwRecoverTransactionManager</b>. Calling <b>TmRecoverTransactionManager</b> with a non-<b>NULL</b> <i>TargetVirtualClock</i> parameter value is functionally equivalent to calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff567089">ZwRollforwardTransactionManager</a>. 

For more information about recovery operations, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567079">ZwRecoverTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567089">ZwRollforwardTransactionManager</a>
 

 


---
UID: NF:wdm.ZwRollforwardTransactionManager
title: ZwRollforwardTransactionManager function (wdm.h)
description: The ZwRollforwardTransactionManager routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager.
old-location: kernel\zwrollforwardtransactionmanager.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ZwRollforwardTransactionManager function"]
ms.keywords: NtRollforwardTransactionManager, ZwRollforwardTransactionManager, ZwRollforwardTransactionManager routine [Kernel-Mode Driver Architecture], kernel.zwrollforwardtransactionmanager, ktm_ref_79b2cde2-5fd0-431f-a776-f4cd6fda1e45.xml, wdm/NtRollforwardTransactionManager, wdm/ZwRollforwardTransactionManager
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
 - ZwRollforwardTransactionManager
 - wdm/ZwRollforwardTransactionManager
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwRollforwardTransactionManager
---

# ZwRollforwardTransactionManager function


## -description

The <b>ZwRollforwardTransactionManager</b> routine initiates recovery operations for all of the in-progress transactions that are assigned to a specified transaction manager.

## -parameters

### -param TransactionManagerHandle 

[in]
A handle to a <a href="/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a> that was obtained by a previous call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a> or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransactionmanager">ZwOpenTransactionManager</a>. The handle must have TRANSACTIONMANAGER_RECOVER access to the object.

### -param TmVirtualClock 

[in, optional]
A pointer to a <a href="/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>. For more information about this parameter, see the following Remarks section.

## -returns

<b>ZwRollforwardTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values:

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
The specified handle is not a handle to a transaction manager object.

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
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the transaction manager object.

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
 

The routine might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

The <b>ZwRollforwardTransactionManager</b> routine recovers all logged activity that KTM finds in the transaction manager's log file, up to and including the virtual clock value that the <i>TmVirtualClock</i> parameter supplies. 

Your component can traverse the log file incrementally by calling <b>ZwRollforwardTransactionManager</b> repetitively and setting the <i>VirtualClock</i> parameter to a higher value before each call.

If the <i>TmVirtualClock</i> parameter is <b>NULL</b>, calling <b>ZwRollforwardTransactionManager</b> is equivalent to calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a>. 

For more information about recovery operations, see <a href="/windows-hardware/drivers/kernel/handling-recovery-operations">Handling Recovery Operations</a>.

<b>NtRollforwardTransactionManager</b> and <b>ZwRollforwardTransactionManager</b> are two versions of the same Windows Native System Services routine. The <b>NtRollforwardTransactionManager</b> routine in the Windows kernel is not directly accessible to kernel-mode drivers. However, kernel-mode drivers can access this routine indirectly by calling the <b>ZwRollforwardTransactionManager</b> routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-tmrecovertransactionmanager">TmRecoverTransactionManager</a>



<a href="/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopentransactionmanager">ZwOpenTransactionManager</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a>


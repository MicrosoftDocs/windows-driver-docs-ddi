---
UID: NF:wdm.ZwReadOnlyEnlistment
title: ZwReadOnlyEnlistment function (wdm.h)
description: The ZwReadOnlyEnlistment routine sets a specified enlistment to be read-only.
old-location: kernel\zwreadonlyenlistment.htm
tech.root: kernel
ms.assetid: 4178d9ad-5dd1-40c2-ba23-7625d424cd6d
ms.date: 04/30/2018
keywords: ["ZwReadOnlyEnlistment function"]
ms.keywords: NtReadOnlyEnlistment, ZwReadOnlyEnlistment, ZwReadOnlyEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwreadonlyenlistment, ktm_ref_d6e64da8-cb5c-4564-be5d-65073fc17375.xml, wdm/NtReadOnlyEnlistment, wdm/ZwReadOnlyEnlistment
f1_keywords:
 - "wdm/ZwReadOnlyEnlistment"
 - "ZwReadOnlyEnlistment"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- ZwReadOnlyEnlistment
- NtReadOnlyEnlistment
targetos: Windows
req.typenames: 
---

# ZwReadOnlyEnlistment function


## -description


The <b>ZwReadOnlyEnlistment</b> routine sets a specified enlistment to be read-only.


## -parameters




### -param EnlistmentHandle [in]

A handle to an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a> that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SUBORDINATE_RIGHTS access to the object.


### -param TmVirtualClock [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-virtual-clock-values">virtual clock value</a>. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwReadOnlyEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
<dt><b>STATUS_TRANSACTION_NOT_REQUESTED</b></dt>
</dl>
</td>
<td width="60%">
The transaction or its enlistment is not in the correct state. For example, an enlistment cannot be read-only if the ENLISTMENT_SUPERIOR flag was specified to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>.

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
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



Your component cannot call <b>ZwReadOnlyEnlistment</b> for a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-superior-transaction-manager">superior enlistment</a>.

For more information about <b>ZwReadOnlyEnlistment</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Read-Only Enlistment</a>.

<b>NtReadOnlyEnlistment</b> and <b>ZwReadOnlyEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>
 

 


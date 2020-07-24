---
UID: NF:wdm.ZwQueryInformationEnlistment
title: ZwQueryInformationEnlistment function (wdm.h)
description: The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object.
old-location: kernel\zwqueryinformationenlistment.htm
tech.root: kernel
ms.assetid: d8aa5227-7150-4fb1-a8ab-cb0f8ae4f74a
ms.date: 04/30/2018
keywords: ["ZwQueryInformationEnlistment function"]
ms.keywords: NtQueryInformationEnlistment, ZwQueryInformationEnlistment, ZwQueryInformationEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwqueryinformationenlistment, ktm_ref_f9039d82-41a8-4696-9393-cb9ea0d8d279.xml, wdm/NtQueryInformationEnlistment, wdm/ZwQueryInformationEnlistment
f1_keywords:
 - "wdm/ZwQueryInformationEnlistment"
 - "ZwQueryInformationEnlistment"
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
- ZwQueryInformationEnlistment
- NtQueryInformationEnlistment
targetos: Windows
req.typenames: 
---

# ZwQueryInformationEnlistment function


## -description


The <b>ZwQueryInformationEnlistment</b> routine retrieves information about a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.


## -parameters




### -param EnlistmentHandle [in]

A handle to an enlistment object that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_QUERY_INFORMATION access to the object.


### -param EnlistmentInformationClass [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_enlistment_information_class">ENLISTMENT_INFORMATION_CLASS</a>-typed enumeration value that specifies the information to be obtained. This value must be one of the following values:

<ul>
<li>
<b>EnlistmentBasicInformation</b>

</li>
<li>
<b>EnlistmentRecoveryInformation</b>

</li>
</ul>
The enumeration's <b>EnlistmentFullInformation</b> value is not used with <b>ZwQueryInformationEnlistment</b>. 


### -param EnlistmentInformation [out]

A pointer to a caller-allocated buffer that receives the information that the <i>EnlistmentInformationClass </i>parameter specifies. If the <i>EnlistmentInformationClass</i> parameter's value is <b>EnlistmentBasicInformation</b>, this buffer's structure type must be <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_enlistment_basic_information">ENLISTMENT_BASIC_INFORMATION</a>. If the <i>EnlistmentInformationClass</i> parameter's value is <b>EnlistmentRecoveryInformation</b>, this buffer's type must match the caller-defined type that the caller used when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>.


### -param EnlistmentInformationLength [in]

The length, in bytes, of the buffer that the <i>EnlistmentInformation</i> parameter points to.


### -param ReturnLength [out, optional]

A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>EnlistmentInformation </i>buffer. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwQueryInformationEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
The <i>EnlistmentInformationClass</i> parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The <i>EnlistmentInformationLength</i> parameter's value is invalid.

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



A resource manager can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a> to set enlistment-specific recovery information for an enlistment object and then call <b>ZwQueryInformationEnlistment</b> to retrieve the recovery information.

For more information about <b>ZwQueryInformationEnlistment</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/handling-recovery-operations">Handling Recovery Operations</a>.

Callers of <b>ZwQueryInformationEnlistment</b> must be running at IRQL = PASSIVE_LEVEL.

<b>NtQueryInformationEnlistment</b> and <b>ZwQueryInformationEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_enlistment_basic_information">ENLISTMENT_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_enlistment_information_class">ENLISTMENT_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntsetinformationenlistment">ZwSetInformationEnlistment</a>
 

 


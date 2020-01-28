---
UID: NF:wdm.NtSetInformationEnlistment
title: NtSetInformationEnlistment function (wdm.h)
description: The ZwSetInformationEnlistment routine sets information for a specified enlistment object.
old-location: kernel\zwsetinformationenlistment.htm
tech.root: kernel
ms.assetid: c87547b0-a16e-48b5-91ca-c414c5317ac6
ms.date: 04/30/2018
ms.keywords: NtSetInformationEnlistment, ZwSetInformationEnlistment, ZwSetInformationEnlistment routine [Kernel-Mode Driver Architecture], kernel.zwsetinformationenlistment, ktm_ref_3e37f795-0826-43df-bb96-14f1031437da.xml, wdm/NtSetInformationEnlistment, wdm/ZwSetInformationEnlistment
f1_keywords:
 - "wdm/ZwSetInformationEnlistment"
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
- ZwSetInformationEnlistment
- NtSetInformationEnlistment
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtSetInformationEnlistment function


## -description


The <b>ZwSetInformationEnlistment</b> routine sets information for a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/enlistment-objects">enlistment object</a>.


## -parameters




### -param EnlistmentHandle [in]

A handle to an enlistment object that was obtained by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SET_INFORMATION access to the object.


### -param EnlistmentInformationClass [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_enlistment_information_class">ENLISTMENT_INFORMATION_CLASS</a>-typed enumeration value that specifies the type of information to be set. This value must be <b>EnlistmentRecoveryInformation</b>.

The enumeration's <b>EnlistmentBasicInformation</b> and <b>EnlistmentFullInformation</b> values are not used with <b>ZwSetInformationEnlistment</b>. 


### -param EnlistmentInformation [in]

A pointer to a caller-allocated buffer that contains caller-defined recovery information for the enlistment.


### -param EnlistmentInformationLength [in]

The length, in bytes, of the buffer that the <i>EnlistmentInformation</i> parameter points to.


## -returns



<b>ZwSetInformationEnlistment</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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



A resource manager can use the <b>ZwSetInformationEnlistment</b> routine to set recovery information for an enlistment. KTM writes the recovery information to the log stream, and the resource manager can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a> to read this information from the log stream at any time.

Each subsequent call to <b>ZwSetInformationEnlistment</b> deletes the recovery information that the previous call specified before it stores the new recovery information.

For more information about how to use <b>ZwSetInformationEnlistment</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-log-streams-with-ktm">Using Log Streams with KTM</a>.

<b>NtSetInformationEnlistment</b> and <b>ZwSetInformationEnlistment</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_enlistment_information_class">ENLISTMENT_INFORMATION_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreateenlistment">ZwCreateEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntopenenlistment">ZwOpenEnlistment</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationenlistment">ZwQueryInformationEnlistment</a>
 

 


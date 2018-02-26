---
UID: NF:wdm.NtSetInformationEnlistment
title: NtSetInformationEnlistment function
author: windows-driver-content
description: The ZwSetInformationEnlistment routine sets information for a specified enlistment object.
old-location: kernel\zwsetinformationenlistment.htm
old-project: kernel
ms.assetid: c87547b0-a16e-48b5-91ca-c414c5317ac6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , E, I, N, NtSetInformationEnlistment, S, ZwSetInformationEnlistment, ZwSetInformationEnlistment routine [Kernel-Mode Driver Architecture], a, e, f, i, kernel.zwsetinformationenlistment, ktm_ref_3e37f795-0826-43df-bb96-14f1031437da.xml, l, m, n, o, r, s, t, wdm/NtSetInformationEnlistment, wdm/ZwSetInformationEnlistment"
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
-	ZwSetInformationEnlistment
-	NtSetInformationEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# NtSetInformationEnlistment function


## -description


The <b>ZwSetInformationEnlistment</b> routine sets information for a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.


## -syntax


````
NTSTATUS ZwSetInformationEnlistment(
  _In_ HANDLE                       EnlistmentHandle,
  _In_ ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass,
  _In_ PVOID                        EnlistmentInformation,
  _In_ ULONG                        EnlistmentInformationLength
);
````


## -parameters




### -param EnlistmentHandle [in]

A handle to an enlistment object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_SET_INFORMATION access to the object.


### -param EnlistmentInformationClass [in]

A <a href="..\wdm\ne-wdm-_enlistment_information_class.md">ENLISTMENT_INFORMATION_CLASS</a>-typed enumeration value that specifies the type of information to be set. This value must be <b>EnlistmentRecoveryInformation</b>.

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
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A resource manager can use the <b>ZwSetInformationEnlistment</b> routine to set recovery information for an enlistment. KTM writes the recovery information to the log stream, and the resource manager can call <a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a> to read this information from the log stream at any time.

Each subsequent call to <b>ZwSetInformationEnlistment</b> deletes the recovery information that the previous call specified before it stores the new recovery information.

For more information about how to use <b>ZwSetInformationEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565415">Using Log Streams with KTM</a>.

<b>NtSetInformationEnlistment</b> and <b>ZwSetInformationEnlistment</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="..\wdm\ne-wdm-_enlistment_information_class.md">ENLISTMENT_INFORMATION_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>



<a href="..\wdm\nf-wdm-zwqueryinformationenlistment.md">ZwQueryInformationEnlistment</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationEnlistment routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


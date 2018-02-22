---
UID: NF:wdm.NtQueryInformationEnlistment
title: NtQueryInformationEnlistment function
author: windows-driver-content
description: The ZwQueryInformationEnlistment routine retrieves information about a specified enlistment object.
old-location: kernel\zwqueryinformationenlistment.htm
old-project: kernel
ms.assetid: d8aa5227-7150-4fb1-a8ab-cb0f8ae4f74a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ZwQueryInformationEnlistment routine [Kernel-Mode Driver Architecture], ZwQueryInformationEnlistment, kernel.zwqueryinformationenlistment, ktm_ref_f9039d82-41a8-4696-9393-cb9ea0d8d279.xml, wdm/NtQueryInformationEnlistment, wdm/ZwQueryInformationEnlistment, NtQueryInformationEnlistment
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
-	ZwQueryInformationEnlistment
-	NtQueryInformationEnlistment
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# NtQueryInformationEnlistment function


## -description


The <b>ZwQueryInformationEnlistment</b> routine retrieves information about a specified <a href="https://msdn.microsoft.com/80e61475-4bb7-4eaa-b9f1-ff95eac9bc77">enlistment object</a>.


## -syntax


````
NTSTATUS ZwQueryInformationEnlistment(
  _In_      HANDLE                       EnlistmentHandle,
  _In_      ENLISTMENT_INFORMATION_CLASS EnlistmentInformationClass,
  _Out_     PVOID                        EnlistmentInformation,
  _In_      ULONG                        EnlistmentInformationLength,
  _Out_opt_ PULONG                       ReturnLength
);
````


## -parameters




### -param EnlistmentHandle [in]

A handle to an enlistment object that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a> or <a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>. The handle must have ENLISTMENT_QUERY_INFORMATION access to the object.


### -param EnlistmentInformationClass [in]

An <a href="..\wdm\ne-wdm-_enlistment_information_class.md">ENLISTMENT_INFORMATION_CLASS</a>-typed enumeration value that specifies the information to be obtained. This value must be one of the following values:

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

A pointer to a caller-allocated buffer that receives the information that the <i>EnlistmentInformationClass </i>parameter specifies. If the <i>EnlistmentInformationClass</i> parameter's value is <b>EnlistmentBasicInformation</b>, this buffer's structure type must be <a href="..\wdm\ns-wdm-_enlistment_basic_information.md">ENLISTMENT_BASIC_INFORMATION</a>. If the <i>EnlistmentInformationClass</i> parameter's value is <b>EnlistmentRecoveryInformation</b>, this buffer's type must match the caller-defined type that the caller used when it called <a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>.


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
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



A resource manager can call <a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a> to set enlistment-specific recovery information for an enlistment object and then call <b>ZwQueryInformationEnlistment</b> to retrieve the recovery information.

For more information about <b>ZwQueryInformationEnlistment</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

Callers of <b>ZwQueryInformationEnlistment</b> must be running at IRQL = PASSIVE_LEVEL.

<b>NtQueryInformationEnlistment</b> and <b>ZwQueryInformationEnlistment</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\nf-wdm-zwcreateenlistment.md">ZwCreateEnlistment</a>



<a href="..\wdm\nf-wdm-zwopenenlistment.md">ZwOpenEnlistment</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\ne-wdm-_enlistment_information_class.md">ENLISTMENT_INFORMATION_CLASS</a>



<a href="..\wdm\ns-wdm-_enlistment_basic_information.md">ENLISTMENT_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwsetinformationenlistment.md">ZwSetInformationEnlistment</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryInformationEnlistment routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


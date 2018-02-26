---
UID: NF:wdm.ZwQueryInformationTransactionManager
title: ZwQueryInformationTransactionManager function
author: windows-driver-content
description: The ZwQueryInformationTransactionManager routine retrieves information about a specified transaction manager object.
old-location: kernel\zwqueryinformationtransactionmanager.htm
old-project: kernel
ms.assetid: c87e0635-ad0a-4832-97ed-30c731559fb9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , I, M, NtQueryInformationTransactionManager, Q, T, Z, ZwQueryInformationTransactionManager, ZwQueryInformationTransactionManager routine [Kernel-Mode Driver Architecture], a, c, e, f, g, i, kernel.zwqueryinformationtransactionmanager, ktm_ref_3311322f-0cc0-4198-8c80-1b203403b080.xml, m, n, o, r, s, t, u, w, wdm/NtQueryInformationTransactionManager, wdm/ZwQueryInformationTransactionManager, y"
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
-	ZwQueryInformationTransactionManager
-	NtQueryInformationTransactionManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwQueryInformationTransactionManager function


## -description


The <b>ZwQueryInformationTransactionManager</b> routine retrieves information about a specified transaction manager object.


## -syntax


````
NTSTATUS ZwQueryInformationTransactionManager(
  _In_      HANDLE                               TransactionManagerHandle,
  _In_      TRANSACTIONMANAGER_INFORMATION_CLASS TransactionManagerInformationClass,
  _Out_     PVOID                                TransactionManagerInformation,
  _In_      ULONG                                TransactionManagerInformationLength,
  _Out_opt_ PULONG                               ReturnLength
);
````


## -parameters




### -param TransactionManagerHandle [in]

A handle to a <a href="https://msdn.microsoft.com/af53cda4-e2ab-47df-9311-a4da2a2ee08d">transaction manager object</a> that was obtained by a previous call to <a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a> or <a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>. The handle must have TRANSACTIONMANAGER_QUERY_INFORMATION access to the object.


### -param TransactionManagerInformationClass [in]

A <a href="..\wdm\ne-wdm-_transactionmanager_information_class.md">TRANSACTIONMANAGER_INFORMATION_CLASS</a>-typed enumeration value that specifies the information to be obtained. This value must be one of the following:

<ul>
<li>
<b>TransactionManagerBasicInformation</b>

</li>
<li>
<b>TransactionManagerLogInformation</b>

</li>
<li>
<b>TransactionManagerLogPathInformation</b>

</li>
</ul>
The enumeration's <b>TransactionManagerOnlineProbeInformation</b> value is not used with <b>ZwQueryInformationTransactionManager</b>. 


### -param TransactionManagerInformation [out]

A pointer to a caller-allocated buffer that receives the information that the <i>TransactionManagerInformationClass</i> parameter specifies. The buffer's structure type must be <a href="..\wdm\ns-wdm-_transactionmanager_basic_information.md">TRANSACTIONMANAGER_BASIC_INFORMATION</a>, <a href="..\wdm\ns-wdm-_transactionmanager_log_information.md">TRANSACTIONMANAGER_LOG_INFORMATION</a>, <a href="..\wdm\ns-wdm-_transactionmanager_logpath_information.md">TRANSACTIONMANAGER_LOGPATH_INFORMATION</a>, or <a href="..\wdm\ns-wdm-_transactionmanager_recovery_information.md">TRANSACTIONMANAGER_RECOVERY_INFORMATION</a>.


### -param TransactionManagerInformationLength [in]

The length, in bytes, of the buffer that the <i>TransactionManagerInformation</i> parameter points to, including the length of any additional array elements that the caller has allocated to receive information.


### -param ReturnLength [out, optional]

A pointer to a caller-allocated variable that receives the length, in bytes, of the information that KTM writes to the <i>TransactionManagerInformation</i> buffer. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>ZwQueryInformationTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
The <i>TransactionManagerInformationClass</i> parameter's value is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The length of the buffer that is specified by the <i>TransactionManagerInformationLength </i>parameter is incorrect.

</td>
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
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer that is specified by the <i>TransactionManagerInformation </i>parameter is too small.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



For more information about how to use <b>ZwQueryInformationTransactionManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565415">Using Log Streams with KTM</a>.

<b>NtQueryInformationTransactionManager</b> and <b>ZwQueryInformationTransactionManager</b> are two versions of the same Windows Native System Services routine.

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also

<a href="..\wdm\ns-wdm-_transactionmanager_logpath_information.md">TRANSACTIONMANAGER_LOGPATH_INFORMATION</a>



<a href="..\wdm\ns-wdm-_transactionmanager_log_information.md">TRANSACTIONMANAGER_LOG_INFORMATION</a>



<a href="..\wdm\ne-wdm-_transactionmanager_information_class.md">TRANSACTIONMANAGER_INFORMATION_CLASS</a>



<a href="..\wdm\nf-wdm-zwrollforwardtransactionmanager.md">ZwRollforwardTransactionManager</a>



<a href="..\wdm\nf-wdm-zwcreatetransactionmanager.md">ZwCreateTransactionManager</a>



<a href="..\wdm\ns-wdm-_transactionmanager_basic_information.md">TRANSACTIONMANAGER_BASIC_INFORMATION</a>



<a href="..\wdm\nf-wdm-zwopentransactionmanager.md">ZwOpenTransactionManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="..\wdm\nf-wdm-zwrecovertransactionmanager.md">ZwRecoverTransactionManager</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwQueryInformationTransactionManager routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


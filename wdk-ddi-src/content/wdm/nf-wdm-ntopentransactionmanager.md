---
UID: NF:wdm.NtOpenTransactionManager
title: NtOpenTransactionManager function (wdm.h)
description: The ZwOpenTransactionManager routine obtains a handle to an existing transaction manager object.
old-location: kernel\zwopentransactionmanager.htm
tech.root: kernel
ms.assetid: b3eb40ad-cda9-4a2f-a794-670bd2ee9102
ms.date: 04/30/2018
ms.keywords: NtOpenTransactionManager, ZwOpenTransactionManager, ZwOpenTransactionManager routine [Kernel-Mode Driver Architecture], kernel.zwopentransactionmanager, ktm_ref_26c2e5a4-0a1b-4d75-994a-88f45e213fe3.xml, wdm/NtOpenTransactionManager, wdm/ZwOpenTransactionManager
f1_keywords:
 - "wdm/ZwOpenTransactionManager"
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
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
- ZwOpenTransactionManager
- NtOpenTransactionManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtOpenTransactionManager function


## -description


The <b>ZwOpenTransactionManager</b> routine obtains a handle to an existing transaction manager object.


## -parameters




### -param TmHandle [out]

A pointer to a caller-allocated variable that receives a handle to the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-manager-objects">transaction manager object</a> if <b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS.


### -param DesiredAccess [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that specifies the caller's requested access to the transaction manager object. For information about how to specify this parameter, see the <i>DesiredAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a>. 


### -param ObjectAttributes [in, optional]

A pointer to an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use the <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a> routine to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. This parameter is optional and can be <b>NULL</b>. 


### -param LogFileName [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path and file name of the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-log-streams-with-ktm">log file stream</a> that was created when the transaction manager object was created. For more information, see the <i>LogFileName</i> parameter of <b>ZwCreateTransactionManager</b>. This parameter is optional and can be <b>NULL</b>. 


### -param TmIdentity [in, optional]

A pointer to a GUID that identifies the transaction manager object.  This parameter is optional and can be <b>NULL</b>. 


### -param OpenOptions [in, optional]

This parameter is not used and must be zero.


## -returns



<b>ZwOpenTransactionManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The value of an input parameter is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
KTM could not allocate system resources (typically memory).

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The object name that the <i>ObjectAttributes </i>parameter specifies is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_LOG_CORRUPTION_DETECTED</b></dt>
</dl>
</td>
<td width="60%">
KTM encountered an error while creating or opening the log file.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The value of the <i>DesiredAccess</i> parameter is invalid.

</td>
</tr>
</table>
 

The routine might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



The caller can identify which transaction manager object to open by using one of the following three techniques:

<ul>
<li>
Use the <i>LogFileName</i> parameter to specify the path and file name of a log file stream that was created when the transaction manager object was created.

</li>
<li>
Use the <i>TmIdentity</i> parameter to specify the GUID that identifies the transaction manager object. 

</li>
<li>
Use the <i>ObjectAttributes</i> parameter to supply an <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a> structure that contains the object name that the caller previously specified to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a> routine. 

</li>
</ul>
You must specify only one of the above-listed parameters (an object name, a log file name, or a GUID) and set the other two parameters to <b>NULL</b>.

Your TPS component must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntrecovertransactionmanager">ZwRecoverTransactionManager</a> after it has called <b>ZwOpenTransactionManager</b>.

A TPS component that calls <b>ZwOpenTransactionManager</b> must eventually call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a> to close the object handle.

For more information about how to use <b>ZwOpenTransactionManager</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/transaction-manager-objects">Transaction Manager Objects</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/creating-a-resource-manager">Creating a Resource Manager</a>.

<b>NtOpenTransactionManager</b> and <b>ZwOpenTransactionManager</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/nf-ntdef-initializeobjectattributes">InitializeObjectAttributes</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_object_attributes">OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntclose">ZwClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntcreatetransactionmanager">ZwCreateTransactionManager</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ntqueryinformationtransactionmanager">ZwQueryInformationTransactionManager</a>
 

 


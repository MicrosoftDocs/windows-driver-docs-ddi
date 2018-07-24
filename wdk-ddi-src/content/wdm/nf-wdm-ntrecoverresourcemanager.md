---
UID: NF:wdm.NtRecoverResourceManager
title: NtRecoverResourceManager function
author: windows-driver-content
description: The ZwRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object.
old-location: kernel\zwrecoverresourcemanager.htm
tech.root: kernel
ms.assetid: 976ea17c-db43-487d-a378-3d65d12ddc98
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: NtRecoverResourceManager, ZwRecoverResourceManager, ZwRecoverResourceManager routine [Kernel-Mode Driver Architecture], kernel.zwrecoverresourcemanager, ktm_ref_88d3ee88-7520-4942-95cc-38e53ab14044.xml, wdm/NtRecoverResourceManager, wdm/ZwRecoverResourceManager
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntifs.h
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
api_name:
-	ZwRecoverResourceManager
-	NtRecoverResourceManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# NtRecoverResourceManager function


## -description


The <b>ZwRecoverResourceManager</b> routine tries to recover the transaction that is associated with each enlistment of a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -parameters




### -param ResourceManagerHandle [in]

A handle to a resource manager object that was obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>. The handle must have RESOURCEMANAGER_RECOVER access to the object.


## -returns



<b>ZwRecoverResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return one of the following values: 

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
The specified handle is not a handle to a resource manager object.

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
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>
</td>
<td width="60%">
The transaction manager that is associated with the specified resource manager is not available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have appropriate access to the resource manager object.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



When a resource manager calls <b>ZwRecoverResourceManager</b>, KTM sends a TRANSACTION_NOTIFY_RECOVER notification to the resource manager for each of the resource manager's enlistments. (If the enlistment is a superior enlistment, KTM sends TRANSACTION_NOTIFY_RECOVER_QUERY instead of TRANSACTION_NOTIFY_RECOVER.)

The final notification that KTM sends to the resource manager is TRANSACTION_NOTIFY_LAST_RECOVER.

For more information about <b>ZwRecoverResourceManager</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546922">Handling Recovery Operations</a>.

<b>NtRecoverResourceManager</b> and <b>ZwRecoverResourceManager</b> are two versions of the same Windows Native System Services routine. 

For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564714">TmRecoverResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567054">ZwQueryInformationResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567098">ZwSetInformationResourceManager</a>
 

 


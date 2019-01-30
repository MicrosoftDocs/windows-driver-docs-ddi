---
UID: NF:wdm.TmRecoverResourceManager
title: TmRecoverResourceManager function (wdm.h)
description: The TmRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object.
old-location: kernel\tmrecoverresourcemanager.htm
tech.root: kernel
ms.assetid: d327ea40-ce4d-4218-a367-919240a5a60c
ms.date: 04/30/2018
ms.keywords: TmRecoverResourceManager, TmRecoverResourceManager routine [Kernel-Mode Driver Architecture], kernel.tmrecoverresourcemanager, ktm_ref_e3f0b5e1-18fc-4edf-9270-f6d01e458166.xml, wdm/TmRecoverResourceManager
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
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
api_name:
-	TmRecoverResourceManager
product:
- Windows
targetos: Windows
req.typenames: 
---

# TmRecoverResourceManager function


## -description


The <b>TmRecoverResourceManager</b> routine tries to recover the transaction that is associated with each enlistment of a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -parameters




### -param ResourceManager [in]

A pointer to a resource manager object. To obtain this pointer, your component must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a> provided.


## -returns



<b>TmRecoverResourceManager</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine might return the following value:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_TRANSACTIONMANAGER_NOT_ONLINE</b></dt>
</dl>
</td>
<td width="60%">
The transaction manager that is associated with the specified resource manager is not online.

</td>
</tr>
</table>
 

The routine might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>TmRecoverResourceManager</b> routine is a pointer-based version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567078">ZwRecoverResourceManager</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566427">ZwCreateResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567026">ZwOpenResourceManager</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567078">ZwRecoverResourceManager</a>
 

 


---
UID: NF:wdm.TmRecoverResourceManager
title: TmRecoverResourceManager function
author: windows-driver-content
description: The TmRecoverResourceManager routine tries to recover the transaction that is associated with each enlistment of a specified resource manager object.
old-location: kernel\tmrecoverresourcemanager.htm
old-project: kernel
ms.assetid: d327ea40-ce4d-4218-a367-919240a5a60c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/TmRecoverResourceManager, ktm_ref_e3f0b5e1-18fc-4edf-9270-f6d01e458166.xml, kernel.tmrecoverresourcemanager, TmRecoverResourceManager routine [Kernel-Mode Driver Architecture], TmRecoverResourceManager
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
-	Ext-MS-Win-ntos-tm-l1-1-0.dll
-	tm.sys
apiname: 
-	TmRecoverResourceManager
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# TmRecoverResourceManager function


## -description


The <b>TmRecoverResourceManager</b> routine tries to recover the transaction that is associated with each enlistment of a specified <a href="https://msdn.microsoft.com/b44f2035-ee9f-453b-b12d-89ca36a8b280">resource manager object</a>.


## -syntax


````
NTSTATUS TmRecoverResourceManager(
  _In_ PKRESOURCEMANAGER ResourceManager
);
````


## -parameters




### -param ResourceManager [in]

A pointer to a resource manager object. To obtain this pointer, your component must call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a> and supply the object handle that a previous call to <a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a> or <a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a> provided.


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


The <b>TmRecoverResourceManager</b> routine is a pointer-based version of the <a href="..\wdm\nf-wdm-zwrecoverresourcemanager.md">ZwRecoverResourceManager</a> routine.

For information about when to use KTM's <b>Tm<i>Xxx</i></b> routines instead of <b>Zw<i>Xxx</i></b> routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565567">Using TmXxx Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

<a href="..\wdm\nf-wdm-zwopenresourcemanager.md">ZwOpenResourceManager</a>

<a href="..\wdm\nf-wdm-zwrecoverresourcemanager.md">ZwRecoverResourceManager</a>

<a href="..\wdm\nf-wdm-zwcreateresourcemanager.md">ZwCreateResourceManager</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20TmRecoverResourceManager routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


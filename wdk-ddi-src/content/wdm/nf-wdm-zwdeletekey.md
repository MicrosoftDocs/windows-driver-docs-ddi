---
UID: NF:wdm.ZwDeleteKey
title: ZwDeleteKey function
author: windows-driver-content
description: The ZwDeleteKey routine deletes an open key from the registry.
old-location: kernel\zwdeletekey.htm
old-project: kernel
ms.assetid: 16bde6b6-6e05-4a4d-a0c3-79bb811305d1
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: NtDeleteKey, ZwDeleteKey, ZwDeleteKey routine [Kernel-Mode Driver Architecture], k111_b55bc28e-3539-424e-86b5-f7457e90cc61.xml, kernel.zwdeletekey, wdm/NtDeleteKey, wdm/ZwDeleteKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
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
-	ZwDeleteKey
-	NtDeleteKey
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwDeleteKey function


## -description


The <b>ZwDeleteKey</b> routine deletes an open key from the registry.


## -parameters




### -param KeyHandle [in]

Handle to the registry key to be deleted. The handle is created by a successful call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>. 


## -returns



<b>ZwDeleteKey</b> returns an NTSTATUS value. Possible return values include:




## -remarks



The handle must have been opened for DELETE access for this routine to succeed. For more information, see the <i>DesiredAccess</i> parameter for <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>.

A call to <b>ZwDeleteKey</b> causes the handle that is specified in the <i>KeyHandle</i> parameter—and all other handles to the deleted key—to become invalid. After a call to <b>ZwDeleteKey</b> invalidates the key handles, you must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close the key handles.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtDeleteKey</b>" instead of "<b>ZwDeleteKey</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567014">ZwOpenKey</a>
 

 


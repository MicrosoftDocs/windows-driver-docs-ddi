---
UID: NF:wdm.ZwOpenKey
title: ZwOpenKey function
author: windows-driver-content
description: The ZwOpenKey routine opens an existing registry key.
old-location: kernel\zwopenkey.htm
tech.root: kernel
ms.assetid: e92f0297-8bfc-496d-a00b-e7b5711c7856
ms.date: 04/30/2018
ms.keywords: ZwOpenKey, ZwOpenKey routine [Kernel-Mode Driver Architecture], k111_8583b145-a6be-4e4f-8e46-ca7d48b8a07f.xml, kernel.zwopenkey, wdm/ZwOpenKey
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, PowerIrpDDis, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate, ZwRegistryOpen(storport)
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
-	ZwOpenKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# ZwOpenKey function


## -description


The <b>ZwOpenKey</b> routine opens an existing registry key. 


## -parameters




### -param KeyHandle [out]

Pointer to the HANDLE variable that receives the handle to the key.


### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that determines the requested access to the object. For more information, see the <i>DesiredAccess</i> parameter of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>. 


### -param ObjectAttributes [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff557749">OBJECT_ATTRIBUTES</a> structure that specifies the object name and other attributes. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a> to initialize this structure. If the caller is not running in a system thread context, it must set the OBJ_KERNEL_HANDLE attribute when it calls <b>InitializeObjectAttributes</b>. 


## -returns



<b>ZwOpenKey</b> returns STATUS_SUCCESS if the given key was opened. Otherwise, it can return an error status, including the following:

STATUS_INVALID_HANDLE

STATUS_ACCESS_DENIED 


## -remarks



<b>ZwOpenKey</b> supplies a handle that the caller can use to manipulate a registry key. The routine provides a subset of the functionality of <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

If the specified key does not exist, <b>ZwOpenKey</b> returns an error status and does not return a key handle.

Once the handle pointed to by <i>KeyHandle</i> is no longer in use, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff566417">ZwClose</a> to close it.

<b>ZwOpenKey</b> ignores the security information in the structure that the <i>ObjectAttributes</i> parameter points to.

If the caller is not running in a system thread context, it must ensure that any handles it creates are private handles. Otherwise, the handle can be accessed by the process in whose context the driver is running. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557758">Object Handles</a>.

For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.

<div class="alert"><b>Note</b>    If the call to this function occurs in user mode, you should use the name "<b>NtOpenKey</b>" instead of "<b>ZwOpenKey</b>".</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547804">InitializeObjectAttributes</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566437">ZwDeleteKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566447">ZwEnumerateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566453">ZwEnumerateValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566457">ZwFlushKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567060">ZwQueryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567069">ZwQueryValueKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567109">ZwSetValueKey</a>
 

 


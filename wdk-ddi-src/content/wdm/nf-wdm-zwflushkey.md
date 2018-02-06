---
UID: NF:wdm.ZwFlushKey
title: ZwFlushKey function
author: windows-driver-content
description: The ZwFlushKey routine forces a registry key to be committed to disk.
old-location: kernel\zwflushkey.htm
old-project: kernel
ms.assetid: c5250b7d-a996-4591-b289-cfb1af00e7da
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/NtFlushKey, k111_2831bd9f-93c1-4377-9f0e-26d4ef20e095.xml, kernel.zwflushkey, NtFlushKey, wdm/ZwFlushKey, ZwFlushKey, ZwFlushKey routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlZwPassive, ZwRegistryCreate, ZwRegistryOpen, HwStorPortProhibitedDDIs, ZwRegistryCreate(storport), ZwRegistryOpen(storport)
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
-	ZwFlushKey
-	NtFlushKey
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ZwFlushKey function


## -description


The <b>ZwFlushKey</b> routine forces a registry key to be committed to disk.


## -syntax


````
NTSTATUS ZwFlushKey(
  _In_ HANDLE KeyHandle
);
````


## -parameters




### -param KeyHandle [in]

Handle to the registry key to be flushed to disk. This handle is created by a successful call to <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>.


## -returns


<b>ZwFlushKey</b> returns STATUS_SUCCESS if the key information was transferred to disk, or the appropriate error code on failure.



## -remarks


You can flush changes made by <a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a> or <a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a> by calling <b>ZwFlushKey</b>. This routine does not return until all the changed data that is associated with <i>KeyHandle</i> has been written to disk. <b>ZwFlushKey</b> flushes the entire registry hive for the key, which includes every subkey of the key specified.
<div class="alert"><b>Note</b>    This routine can flush the entire registry. Accordingly, it can generate a great deal of I/O. Since the system flushes key changes automatically every few seconds, you seldom need to call <b>ZwFlushKey</b>.</div><div> </div>For more information about working with registry keys, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565537">Using the Registry in a Driver</a>.
<div class="alert"><b>Note</b>  If the call to this function occurs in user mode, you should use the name "<b>NtFlushKey</b>" instead of "<b>ZwFlushKey</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.



## -see-also

<a href="..\wdm\nf-wdm-zwopenkey.md">ZwOpenKey</a>

<a href="..\wdm\nf-wdm-zwsetvaluekey.md">ZwSetValueKey</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\wdm\nf-wdm-zwcreatekey.md">ZwCreateKey</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwFlushKey routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


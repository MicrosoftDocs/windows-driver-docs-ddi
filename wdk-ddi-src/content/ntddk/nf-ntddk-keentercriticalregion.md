---
UID: NF:ntddk.KeEnterCriticalRegion
title: KeEnterCriticalRegion function
author: windows-driver-content
description: The KeEnterCriticalRegion routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running.
old-location: kernel\keentercriticalregion.htm
tech.root: kernel
ms.assetid: 87826cc7-2710-4582-a324-365dd34e2d0d
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: KeEnterCriticalRegion, KeEnterCriticalRegion routine [Kernel-Mode Driver Architecture], k105_cfa63781-e7c6-455a-8e99-4b20872a0b3f.xml, kernel.keentercriticalregion, wdm/KeEnterCriticalRegion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CriticalRegions, IrqlKeApcLte2, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeEnterCriticalRegion
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeEnterCriticalRegion function


## -description


The <b>KeEnterCriticalRegion</b> routine temporarily disables the execution of normal kernel APCs, but does not prevent special kernel APCs from running.


## -parameters






## -returns



None




## -remarks



A driver calls this routine to enter a critical region in which the execution of normal kernel APCs is deferred until this driver exits the critical region by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a> routine. Any caller of <b>KeEnterCriticalRegion</b> should call <b>KeLeaveCriticalRegion</b> as quickly as possible after entering a critical region.

Highest-level drivers can call <b>KeEnterCriticalRegion</b> while running in the context of the thread that requested the current I/O operation.

A thread that is inside a critical region has both user APCs and normal kernel APCs disabled, but not special kernel APCs. For more information about these APC types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564853">Types of APCs</a>.

Critical regions can be entered recursively and each call to <b>KeEnterCriticalRegion</b> must have a matching call to <b>KeLeaveCriticalRegion</b>.

A driver can use a critical region to acquire and release exclusive access to a shared resource. In this case, the <a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/dn308551">ExReleaseResourceAndLeaveCriticalRegion</a> routines can be used instead of the <b>KeEnterCriticalRegion</b> and <b>KeLeaveCriticalRegion</b> routines. For more information, see the code example in <a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a>.

For more information about APCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540625">Asynchronous Procedure Calls</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn308550">ExEnterCriticalRegionAndAcquireResourceExclusive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn308551">ExReleaseResourceAndLeaveCriticalRegion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551938">KeAreApcsDisabled</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552964">KeLeaveCriticalRegion</a>
 

 


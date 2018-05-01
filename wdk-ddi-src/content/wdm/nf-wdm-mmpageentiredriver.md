---
UID: NF:wdm.MmPageEntireDriver
title: MmPageEntireDriver function
author: windows-driver-content
description: The MmPageEntireDriver routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.
old-location: kernel\mmpageentiredriver.htm
old-project: kernel
ms.assetid: 467a8e64-c4ed-4bd0-81f8-b792367d33bf
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: MmPageEntireDriver, MmPageEntireDriver routine [Kernel-Mode Driver Architecture], k106_2e2de4d8-8b4f-4f8b-9451-f4f1ea8a5325.xml, kernel.mmpageentiredriver, wdm/MmPageEntireDriver
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
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
-	MmPageEntireDriver
product: Windows
targetos: Windows
req.typenames: 
---

# MmPageEntireDriver function


## -description


The <b>MmPageEntireDriver</b> routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.


## -parameters




### -param AddressWithinSection [in]

Pointer to a virtual address within the driver (for example, the address of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> routine).


## -returns



<b>MmPageEntireDriver</b> returns a pointer to the beginning of the driver image in memory.




## -remarks



Use this routine to force a driver to be completely pageable. Drivers that call <b>MmPageEntireDriver</b> must not have an <a href="https://msdn.microsoft.com/library/windows/hardware/ff547958">InterruptService</a> routine (ISR) registered for any interrupts. If the interrupt occurs while the driver is paged out, the system issues a bug check.

The effect of a call to <b>MmPageEntireDriver</b> can be undone by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554680">MmResetDriverPaging</a>.

If the driver is already completely pageable, calling <b>MmPageEntireDriver</b> has no effect. For more information about paging an entire driver, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554346">Making Drivers Pageable</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554601">MmLockPagableCodeSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554607">MmLockPagableDataSection</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554610">MmLockPagableSectionByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554680">MmResetDriverPaging</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556377">MmUnlockPagableImageSection</a>
 

 


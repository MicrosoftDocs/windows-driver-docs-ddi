---
UID: NF:wdm.MmPageEntireDriver
title: MmPageEntireDriver function (wdm.h)
description: The MmPageEntireDriver routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.
old-location: kernel\mmpageentiredriver.htm
tech.root: kernel
ms.assetid: 467a8e64-c4ed-4bd0-81f8-b792367d33bf
ms.date: 04/30/2018
keywords: ["MmPageEntireDriver function"]
ms.keywords: MmPageEntireDriver, MmPageEntireDriver routine [Kernel-Mode Driver Architecture], k106_2e2de4d8-8b4f-4f8b-9451-f4f1ea8a5325.xml, kernel.mmpageentiredriver, wdm/MmPageEntireDriver
f1_keywords:
 - "wdm/MmPageEntireDriver"
 - "MmPageEntireDriver"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmPageEntireDriver
targetos: Windows
req.typenames: 
---

# MmPageEntireDriver function


## -description


The <b>MmPageEntireDriver</b> routine causes all of a driver's code and data to be made pageable, overriding the attributes of the various sections that make up the driver's image.


## -parameters




### -param AddressWithinSection [in]

Pointer to a virtual address within the driver (for example, the address of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine).


## -returns



<b>MmPageEntireDriver</b> returns a pointer to the beginning of the driver image in memory.




## -remarks



Use this routine to force a driver to be completely pageable. Drivers that call <b>MmPageEntireDriver</b> must not have an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-kservice_routine">InterruptService</a> routine (ISR) registered for any interrupts. If the interrupt occurs while the driver is paged out, the system issues a bug check.

The effect of a call to <b>MmPageEntireDriver</b> can be undone by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmresetdriverpaging">MmResetDriverPaging</a>.

If the driver is already completely pageable, calling <b>MmPageEntireDriver</b> has no effect. For more information about paging an entire driver, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/making-drivers-pageable">Making Drivers Pageable</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmlockpagablesectionbyhandle">MmLockPagableSectionByHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmresetdriverpaging">MmResetDriverPaging</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpagableimagesection">MmUnlockPagableImageSection</a>
 

 


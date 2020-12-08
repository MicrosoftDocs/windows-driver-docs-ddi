---
UID: NF:wdm.MmResetDriverPaging
title: MmResetDriverPaging function (wdm.h)
description: The MmResetDriverPaging routine resets the pageable status of a driver's sections to that specified when the driver was compiled.
old-location: kernel\mmresetdriverpaging.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmResetDriverPaging function"]
ms.keywords: MmResetDriverPaging, MmResetDriverPaging routine [Kernel-Mode Driver Architecture], k106_4b691510-4e1f-4da2-bfba-d008a83ef43e.xml, kernel.mmresetdriverpaging, wdm/MmResetDriverPaging
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MmResetDriverPaging
 - wdm/MmResetDriverPaging
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmResetDriverPaging
---

# MmResetDriverPaging function


## -description

The <b>MmResetDriverPaging</b> routine resets the pageable status of a driver's sections to that specified when the driver was compiled.

## -parameters

### -param AddressWithinSection 

[in]
A pointer to a virtual address in the driver (for example, the address of the <a href="/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine).

## -remarks

<b>MmResetDriverPaging</b> causes those routines that would not normally be pageable, to be locked into memory. Hence, image sections such as .text and .data will be locked in memory if this routine is called.

A driver that calls this routine must do so before enabling interrupts on its device.

A call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmpageentiredriver">MmPageEntireDriver</a> is not a prerequisite to calling this routine. However, calls to <b>MmResetDriverPaging</b> do nothing if the driver's image-section attributes have never been overridden by a call to <b>MmPageEntireDriver</b>.

For more information about paging an entire driver, see <a href="/windows-hardware/drivers/kernel/making-drivers-pageable">Making Drivers Pageable</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagablecodesection">MmLockPagableCodeSection</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmlockpagabledatasection">MmLockPagableDataSection</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-mmlockpagablesectionbyhandle">MmLockPagableSectionByHandle</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmpageentiredriver">MmPageEntireDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmunlockpagableimagesection">MmUnlockPagableImageSection</a>

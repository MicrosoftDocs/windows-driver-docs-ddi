---
UID: NF:wdm.IoCopyCurrentIrpStackLocationToNext
title: IoCopyCurrentIrpStackLocationToNext function (wdm.h)
description: The IoCopyCurrentIrpStackLocationToNext routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.
old-location: kernel\iocopycurrentirpstacklocationtonext.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["IoCopyCurrentIrpStackLocationToNext function"]
ms.keywords: IoCopyCurrentIrpStackLocationToNext, IoCopyCurrentIrpStackLocationToNext routine [Kernel-Mode Driver Architecture], k104_11dd3823-a387-4699-a4c4-db88f8961b37.xml, kernel.iocopycurrentirpstacklocationtonext, wdm/IoCopyCurrentIrpStackLocationToNext
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - IoCopyCurrentIrpStackLocationToNext
 - wdm/IoCopyCurrentIrpStackLocationToNext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoCopyCurrentIrpStackLocationToNext
---

# IoCopyCurrentIrpStackLocationToNext function


## -description

The <b>IoCopyCurrentIrpStackLocationToNext</b> routine copies the IRP stack parameters from the current I/O stack location to the stack location of the next-lower driver.

## -parameters

### -param Irp 

[in, out]
A pointer to the IRP.

## -remarks

A driver calls <b>IoCopyCurrentIrpStackLocationToNext</b> to copy the IRP parameters from its stack location to the next-lower driver's stack location.

After calling this routine, a driver typically sets an I/O completion routine with <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a> before passing the IRP to the next-lower driver with <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>. Drivers that pass on their IRP parameters but do not set an I/O completion routine should call [IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md) instead of this routine.

If your driver calls <b>IoSkipCurrentIrpStackLocation</b>, be careful not to modify the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. In particular, your driver should not modify the <b>IO_STACK_LOCATION</b> structure's <b>Parameters</b> union, and should not call the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a> routine.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending">IoMarkIrpPending</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetcompletionroutine">IoSetCompletionRoutine</a>



[IoSkipCurrentIrpStackLocation](./nf-wdm-ioskipcurrentirpstacklocation.md)
---
UID: NF:wdm.IoSkipCurrentIrpStackLocation
tech.root: 
title: IoSkipCurrentIrpStackLocation
ms.date: 07/16/2021
targetos: Windows
description: "Learn more about: IoSkipCurrentIrpStackLocation"
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - IoSkipCurrentIrpStackLocation
f1_keywords:
 - IoSkipCurrentIrpStackLocation
 - wdm/IoSkipCurrentIrpStackLocation
dev_langs:
 - c++
---

## -description

The **IoSkipCurrentIrpStackLocation** macro modifies the system's [**IO_STACK_LOCATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location) array pointer, so that when the current driver calls the next-lower driver, that driver receives the same **IO_STACK_LOCATION** structure that the current driver received.

## -parameters

### -param Irp

[in, out]
A pointer to the IRP.

## -remarks

When your driver sends an IRP to the next-lower driver, your driver can call **IoSkipCurrentIrpStackLocation** if you do not intend to provide an [_IoCompletion_](/windows-hardware/drivers/ddi/wdm/nc-wdm-io_completion_routine) routine (the address of which is stored in the driver's [**IO_STACK_LOCATION**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location) structure). If you call **IoSkipCurrentIrpStackLocation** before calling [**IoCallDriver**](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver), the next-lower driver receives the same **IO_STACK_LOCATION** that your driver received.

If you intend to provide an _IoCompletion_ routine for the IRP, your driver should call [**IoCopyCurrentIrpStackLocationToNext**](/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext) instead of **IoSkipCurrentIrpStackLocation**. If a badly written driver makes the mistake of calling **IoSkipCurrentIrpStackLocation** and then setting a completion routine, this driver might overwrite a completion routine set by the driver below it.

If the driver has pended an IRP, the driver should not be calling **IoSkipCurrentIrpStackLocation** before it passes the IRP to the next lower driver. If the driver calls **IoSkipCurrentIrpStackLocation** on a pended IRP before passing it to the next lower driver, the SL_PENDING_RETURNED flag is still set in the **Control** member of the I/O stack location for the next driver. Because the next driver owns that stack location and might modify it, it could potentially clear the pending flag. This situation might cause the operating system to issue a bug check or the processing of the IRP to never be completed.

Instead, a driver that has pended an IRP should call **IoCopyCurrentIrpStackLocationToNext** to set up a new stack location for the next lower driver before it calls **IoCallDriver**.

If your driver calls **IoSkipCurrentIrpStackLocation**, be careful not to modify the **IO_STACK_LOCATION** structure in a way that could unintentionally affect the lower driver or the system's behavior with respect to that driver. Examples include modifying the **IO_STACK_LOCATION** structure's **Parameters** union or calling [**IoMarkIrpPending**](/windows-hardware/drivers/ddi/wdm/nf-wdm-iomarkirppending).



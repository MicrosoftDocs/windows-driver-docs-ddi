---
UID: NF:ntifs.PoStartNextPowerIrp
title: PoStartNextPowerIrp function (ntifs.h)
description: The PoStartNextPowerIrp routine in ntifs.h signals the power manager that the driver is ready to handle the next power IRP.
old-location: kernel\postartnextpowerirp.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PoStartNextPowerIrp function"]
ms.keywords: PoStartNextPowerIrp, PoStartNextPowerIrp routine [Kernel-Mode Driver Architecture], kernel.postartnextpowerirp, portn_3e23c20a-d35e-45cd-a2da-3dbc0f249548.xml, wdm/PoStartNextPowerIrp
req.header: ntifs.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PoStartNextPowerIrp
 - ntifs/PoStartNextPowerIrp
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PoStartNextPowerIrp
---

# PoStartNextPowerIrp function (ntifs.h)


## -description

The <b>PoStartNextPowerIrp</b> routine signals the <a href="/windows-hardware/drivers/kernel/power-manager">power manager</a> that the driver is ready to handle the next power <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>. (Windows Server 2003, Windows XP, and Windows 2000 only.)

## -parameters

### -param Irp 

[in, out]
A pointer to an IRP in which the major function code is <a href="/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a>.

## -remarks

Starting with Windows Vista, the driver is not required to call <b>PoStartNextPowerIrp</b> and a call to this routine does not perform a power management operation. However, on Windows Server 2003, Windows XP, and Windows 2000, <b>PoStartNextPowerIrp</b> must be called by every driver in a device stack after the driver is finished with the previous power IRP, if any, and is ready to handle the next power IRP. It must be called once by each driver for every <a href="/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a> or <a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a> request.

Although power IRPs are completed only once, typically by the bus driver for a device, each driver in the device stack must call <b>PoStartNextPowerIrp</b> as the IRP travels down or back up the stack. Even if a driver fails the IRP, the driver must nevertheless call <b>PoStartNextPowerIrp</b> to signal the power manager that it is ready to handle another power IRP.

The driver must call <b>PoStartNextPowerIrp</b> while the current IRP stack location points to the current driver. Therefore, this routine must be called before <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>, [IoSkipCurrentIrpStackLocation](../wdm/nf-wdm-ioskipcurrentirpstacklocation.md), and <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver">PoCallDriver</a>. As a general rule, a driver should call <b>PoStartNextPowerIrp</b> from its <i>IoCompletion</i> routine associated with the IRP or from the callback routine it passed to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>.

Bus drivers must call <b>PoStartNextPowerIrp</b> before completing each IRP.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/kernel/irp-mj-power">IRP_MJ_POWER</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-query-power">IRP_MN_QUERY_POWER</a>



<a href="/windows-hardware/drivers/kernel/irp-mn-set-power">IRP_MN_SET_POWER</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocompleterequest">IoCompleteRequest</a>



[IoSkipCurrentIrpStackLocation](../wdm/nf-wdm-ioskipcurrentirpstacklocation.md)



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-pocalldriver">PoCallDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-porequestpowerirp">PoRequestPowerIrp</a>
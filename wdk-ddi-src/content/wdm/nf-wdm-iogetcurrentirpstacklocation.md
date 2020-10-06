---
UID: NF:wdm.IoGetCurrentIrpStackLocation
title: IoGetCurrentIrpStackLocation function (wdm.h)
description: The IoGetCurrentIrpStackLocation routine returns a pointer to the caller's I/O stack location in the specified IRP.
old-location: kernel\iogetcurrentirpstacklocation.htm
tech.root: kernel
ms.assetid: 75144188-728b-4613-ac69-8cadf0f60233
ms.date: 04/30/2018
keywords: ["IoGetCurrentIrpStackLocation function"]
ms.keywords: IoGetCurrentIrpStackLocation, IoGetCurrentIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_f92e53c7-8a26-4cb0-859b-b0a7be4dce6a.xml, kernel.iogetcurrentirpstacklocation, wdm/IoGetCurrentIrpStackLocation
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
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - IoGetCurrentIrpStackLocation
 - wdm/IoGetCurrentIrpStackLocation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoGetCurrentIrpStackLocation
---

# IoGetCurrentIrpStackLocation function


## -description

The <b>IoGetCurrentIrpStackLocation</b> routine returns a pointer to the caller's I/O stack location in the specified IRP.

## -parameters

### -param Irp 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>.

## -returns

<b>IoGetCurrentIrpStackLocation</b> returns a pointer to an <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure that contains the I/O stack location for the driver.

## -remarks

Every driver must call <b>IoGetCurrentIrpStackLocation</b> with each IRP it is sent in order to get any parameters for the current request. Unless a driver supplies a dispatch routine for each <b>IRP_MJ_<i>XXX</i></b> code that the driver handles, the driver also must check its I/O stack location in the IRP to determine what operation is being requested.

If a driver is passing the same parameters that it received to the next-lower driver, it should call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a> or <a href="/windows-hardware/drivers/kernel/mm-bad-pointer">IoSkipCurrentIrpStackLocation</a> instead of getting a pointer to the next-lower stack location and copying the parameters manually.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_irp">IRP</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetnextirpstacklocation">IoGetNextIrpStackLocation</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetnextirpstacklocation">IoSetNextIrpStackLocation</a>
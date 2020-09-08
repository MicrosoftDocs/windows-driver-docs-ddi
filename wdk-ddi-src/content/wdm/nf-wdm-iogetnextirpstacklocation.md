---
UID: NF:wdm.IoGetNextIrpStackLocation
title: IoGetNextIrpStackLocation function (wdm.h)
description: The IoGetNextIrpStackLocation routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver.
old-location: kernel\iogetnextirpstacklocation.htm
tech.root: kernel
ms.assetid: 44d38686-7a66-4e27-9dc7-9b3b4dbdffd6
ms.date: 04/30/2018
keywords: ["IoGetNextIrpStackLocation function"]
ms.keywords: IoGetNextIrpStackLocation, IoGetNextIrpStackLocation routine [Kernel-Mode Driver Architecture], k104_28da61f1-a732-4336-a14a-90a5bd2682c3.xml, kernel.iogetnextirpstacklocation, wdm/IoGetNextIrpStackLocation
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
 - IoGetNextIrpStackLocation
 - wdm/IoGetNextIrpStackLocation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - IoGetNextIrpStackLocation
---

# IoGetNextIrpStackLocation function


## -description

The <b>IoGetNextIrpStackLocation</b> routine gives a higher level driver access to the next-lower driver's I/O stack location in an IRP so the caller can set it up for the lower driver.

## -parameters

### -param Irp 

[in]
A pointer to the IRP.

## -returns

<b>IoGetNextIrpStackLocation</b> returns a pointer to the next-lower-level driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O stack location</a> in the given IRP.

## -remarks

Each driver that passes IRPs on to lower drivers must set up the stack location for the next lower driver. A driver calls <b>IoGetNextIrpStackLocation</b> to get a pointer to the next-lower driver's I/O stack location.

If a driver is passing the same parameters that it received to the next-lower driver, it should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">IoSkipCurrentIrpStackLocation</a> instead of getting a pointer to the next-lower stack location and copying the parameters manually.

The return value is a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a> structure. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/i-o-stack-locations">I/O Stack Locations</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_stack_location">IO_STACK_LOCATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocalldriver">IoCallDriver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iocopycurrentirpstacklocationtonext">IoCopyCurrentIrpStackLocationToNext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetcurrentirpstacklocation">IoGetCurrentIrpStackLocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetnextirpstacklocation">IoSetNextIrpStackLocation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/mm-bad-pointer">IoSkipCurrentIrpStackLocation</a>


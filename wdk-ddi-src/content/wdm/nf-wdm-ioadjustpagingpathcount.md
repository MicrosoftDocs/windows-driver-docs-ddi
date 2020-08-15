---
UID: NF:wdm.IoAdjustPagingPathCount
title: IoAdjustPagingPathCount macro (wdm.h)
description: The IoAdjustPagingPathCount routine increments or decrements a caller-supplied page-file counter as an atomic operation.
old-location: kernel\ioadjustpagingpathcount.htm
tech.root: kernel
ms.assetid: be353d10-1d8a-4fea-a415-e1729184e451
ms.date: 04/30/2018
keywords: ["IoAdjustPagingPathCount macro"]
ms.keywords: IoAdjustPagingPathCount, IoAdjustPagingPathCount routine [Kernel-Mode Driver Architecture], k104_f52acd6d-f3f6-43c2-a339-3060a12a6298.xml, kernel.ioadjustpagingpathcount, wdm/IoAdjustPagingPathCount
f1_keywords:
 - "wdm/IoAdjustPagingPathCount"
 - "IoAdjustPagingPathCount"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- IoAdjustPagingPathCount
targetos: Windows
req.typenames: 
---

# IoAdjustPagingPathCount macro


## -description


The <b>IoAdjustPagingPathCount</b> routine increments or decrements a caller-supplied page-file counter as an atomic operation.


## -parameters




### -param _count_
[in]
Pointer to a caller-supplied variable that contains a counter. A driver typically stores a page-file counter in the device extension for the device.


### -param _paging_
[in]

Specifies whether the counter is to be incremented or decremented. A value of <b>TRUE</b> specifies an increment operation.


## -remarks



This routine is useful for maintaining a count of paging files on a device. The operating system notifies a driver that a paging file has been created on, or removed from, one of the driver's devices by sending an IRP. The IRP has the major code <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-pnp">IRP_MJ_PNP</a> and the minor code <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-device-usage-notification">IRP_MN_DEVICE_USAGE_NOTIFICATION</a>.

This routine can be used for other counters, such as counters for hibernation files or crash-dump files.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-pnp">IRP_MJ_PNP</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-device-usage-notification">IRP_MN_DEVICE_USAGE_NOTIFICATION</a>
 

 


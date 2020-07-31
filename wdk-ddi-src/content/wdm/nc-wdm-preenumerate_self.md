---
UID: NC:wdm.PREENUMERATE_SELF
title: PREENUMERATE_SELF (wdm.h)
description: A ReenumerateSelf routine requests that a bus driver reenumerate a child device.
old-location: kernel\reenumerateself.htm
tech.root: kernel
ms.assetid: ee669f35-87a5-4c5e-9936-b9135a1459e1
ms.date: 04/30/2018
keywords: ["PREENUMERATE_SELF callback function"]
ms.keywords: PREENUMERATE_SELF, ReenumerateSelf, ReenumerateSelf routine [Kernel-Mode Driver Architecture], drvr_interface_208efec1-4236-441b-a4b8-45a9539e4d84.xml, kernel.reenumerateself, wdm/ReenumerateSelf
f1_keywords:
 - "wdm/ReenumerateSelf"
 - "ReenumerateSelf"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista.
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
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- wdm.h
api_name:
- ReenumerateSelf
targetos: Windows
req.typenames: 
---

# PREENUMERATE_SELF callback function


## -description


A <i>ReenumerateSelf</i> routine requests that a bus driver reenumerate a child device.


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reenumerate_self_interface_standard">REENUMERATE_SELF_INTERFACE_STANDARD</a> structure.


## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reenumerate_self_interface_standard">REENUMERATE_SELF_INTERFACE_STANDARD</a> interface structure supplies a pointer to the <i>ReenumerateSelf</i> routine.

If the bus driver can process the request at the time of the routine call, the bus driver asynchronously reports the device as missing in a subsequent <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a> BusRelations query. This report causes the current device instance to receive <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> requests. After the surprise removal has been processed, a new instance of the device is enumerated and the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_add_device">AddDevice</a> routine is called to rebuild the device stack.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-query-device-relations">IRP_MN_QUERY_DEVICE_RELATIONS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_reenumerate_self_interface_standard">REENUMERATE_SELF_INTERFACE_STANDARD</a>
 

 


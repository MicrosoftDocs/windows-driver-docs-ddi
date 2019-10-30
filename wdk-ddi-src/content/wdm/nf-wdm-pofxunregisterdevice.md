---
UID: NF:wdm.PoFxUnregisterDevice
title: PoFxUnregisterDevice function (wdm.h)
description: The PoFxUnregisterDevice routine removes the registration of a device from the power management framework (PoFx).
old-location: kernel\pofxunregisterdevice.htm
tech.root: kernel
ms.assetid: FC4B1B4D-31D8-4E63-A3A5-07A1099997A8
ms.date: 04/30/2018
ms.keywords: PoFxUnregisterDevice, PoFxUnregisterDevice routine [Kernel-Mode Driver Architecture], kernel.pofxunregisterdevice, wdm/PoFxUnregisterDevice
ms.topic: function
f1_keywords:
 - "wdm/PoFxUnregisterDevice"
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Ntoskrnl.exe
api_name:
- PoFxUnregisterDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxUnregisterDevice function


## -description


The <b>PoFxUnregisterDevice</b> routine removes the registration of a device from the power management framework (PoFx).


## -parameters




### -param Handle [in]

A handle that represents the registration of the device with PoFx. The device driver previously received this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine.


## -returns



None.




## -remarks



The driver that owns the power policy for a device must unregister the device from PoFx when the device is removed. The Plug and Play (PnP) manager can remove the device stack from the PnP tree only after the device is unregistered.

To unregister the device, the driver calls <b>PoFxUnregisterDevice</b> during the handling of an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a> request, whichever is received first. This call should occur after the driver no longer requires access to the device's hardware.

A device driver that calls this routine must previously have called the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a> routine to register the device with PoFx.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-remove-device">IRP_MN_REMOVE_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mn-surprise-removal">IRP_MN_SURPRISE_REMOVAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxregisterdevice">PoFxRegisterDevice</a>
 

 


---
UID: NS:pep_x._PEP_WORK_DEVICE_POWER
title: _PEP_WORK_DEVICE_POWER (pep_x.h)
description: The PEP_WORK_DEVICE_POWER structure describes the new power requirements for the specified device.
old-location: kernel\pep_work_device_power.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_WORK_DEVICE_POWER structure"]
ms.keywords: "*PPEP_WORK_DEVICE_POWER, PEP_WORK_DEVICE_POWER, PEP_WORK_DEVICE_POWER structure [Kernel-Mode Driver Architecture], PPEP_WORK_DEVICE_POWER, PPEP_WORK_DEVICE_POWER structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_DEVICE_POWER, kernel.pep_work_device_power, pep_x/PEP_WORK_DEVICE_POWER, pep_x/PPEP_WORK_DEVICE_POWER"
req.header: pep_x.h
req.include-header: Pepfx.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: 
targetos: Windows
req.typenames: PEP_WORK_DEVICE_POWER, *PPEP_WORK_DEVICE_POWER
f1_keywords:
 - _PEP_WORK_DEVICE_POWER
 - pep_x/_PEP_WORK_DEVICE_POWER
 - PPEP_WORK_DEVICE_POWER
 - pep_x/PPEP_WORK_DEVICE_POWER
 - PEP_WORK_DEVICE_POWER
 - pep_x/PEP_WORK_DEVICE_POWER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pep_x.h
api_name:
 - PEP_WORK_DEVICE_POWER
---

# _PEP_WORK_DEVICE_POWER structure


## -description

The <b>PEP_WORK_DEVICE_POWER</b> structure describes the new power requirements for the specified device.

## -struct-fields

### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx). A POHANDLE value that represents the registration of the device with PoFx. The platform extension plug-in (PEP) previously received this handle from PoFx during the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the device's driver stack registered the device with PoFx.

### -field PowerRequired

Whether the device requires power. Set to TRUE if the device requires power and the device driver <u>must</u> bring the device back to the D0 power state. Set to FALSE if the device is not required to stay turned on and the driver is permitted to transition the device from D0 to a low-power state.

## -remarks

The <b>DevicePower</b> member of the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_DEVICE_POWER</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_work_information">PEP_WORK_INFORMATION</a>

---
UID: NS:pep_x._PEP_UNREGISTER_DEVICE
title: _PEP_UNREGISTER_DEVICE (pep_x.h)
description: The PEP_UNREGISTER_DEVICE structure identifies a device whose registration is being removed from the Windows power management framework (PoFx).
old-location: kernel\pep_unregister_device.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_UNREGISTER_DEVICE structure"]
ms.keywords: "*PPEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE, PEP_UNREGISTER_DEVICE structure [Kernel-Mode Driver Architecture], PPEP_UNREGISTER_DEVICE, PPEP_UNREGISTER_DEVICE structure pointer [Kernel-Mode Driver Architecture], _PEP_UNREGISTER_DEVICE, kernel.pep_unregister_device, pepfx/PEP_UNREGISTER_DEVICE, pepfx/PPEP_UNREGISTER_DEVICE"
req.header: pep_x.h
req.include-header: Pep_x.h
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
req.typenames: PEP_UNREGISTER_DEVICE, *PPEP_UNREGISTER_DEVICE
f1_keywords:
 - _PEP_UNREGISTER_DEVICE
 - pep_x/_PEP_UNREGISTER_DEVICE
 - PPEP_UNREGISTER_DEVICE
 - pep_x/PPEP_UNREGISTER_DEVICE
 - PEP_UNREGISTER_DEVICE
 - pep_x/PEP_UNREGISTER_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_UNREGISTER_DEVICE
---

# _PEP_UNREGISTER_DEVICE structure (pep_x.h)


## -description

The <b>PEP_UNREGISTER_DEVICE</b> structure identifies a device whose registration is being removed from the Windows <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="/windows-hardware/drivers/kernel/using-peps-for-acpi-services">PEP_DPM_UNREGISTER_DEVICE</a>

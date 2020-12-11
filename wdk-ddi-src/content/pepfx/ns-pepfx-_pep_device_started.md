---
UID: NS:pepfx._PEP_DEVICE_STARTED
title: _PEP_DEVICE_STARTED (pepfx.h)
description: The PEP_DEVICE_STARTED structure identifies a device whose driver has completed its registration with the Windows power management framework (PoFx).
old-location: kernel\pep_device_started.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_DEVICE_STARTED structure"]
ms.keywords: "*PPEP_DEVICE_STARTED, PEP_DEVICE_STARTED, PEP_DEVICE_STARTED structure [Kernel-Mode Driver Architecture], PPEP_DEVICE_STARTED, PPEP_DEVICE_STARTED structure pointer [Kernel-Mode Driver Architecture], _PEP_DEVICE_STARTED, kernel.pep_device_started, pepfx/PEP_DEVICE_STARTED, pepfx/PPEP_DEVICE_STARTED"
req.header: pepfx.h
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
req.typenames: PEP_DEVICE_STARTED, *PPEP_DEVICE_STARTED
f1_keywords:
 - _PEP_DEVICE_STARTED
 - pepfx/_PEP_DEVICE_STARTED
 - PPEP_DEVICE_STARTED
 - pepfx/PPEP_DEVICE_STARTED
 - PEP_DEVICE_STARTED
 - pepfx/PEP_DEVICE_STARTED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - PEP_DEVICE_STARTED
---

# _PEP_DEVICE_STARTED structure (pepfx.h)


## -description

The <b>PEP_DEVICE_STARTED</b> structure identifies a device whose driver has completed its registration with the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx).

## -struct-fields

### -field DeviceHandle

[in] A PEPHANDLE value that identifies the device. The PEP supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_started">PEP_DPM_DEVICE_STARTED</a> notification. The <b>DeviceHandle</b> member of this structure contains an input value that is supplied by PoFx.

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_device_started">PEP_DPM_DEVICE_STARTED</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>

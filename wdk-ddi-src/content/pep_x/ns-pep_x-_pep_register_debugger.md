---
UID: NS:pep_x._PEP_REGISTER_DEBUGGER
title: _PEP_REGISTER_DEBUGGER (pep_x.h)
description: The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport.
old-location: kernel\pep_register_debugger.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PEP_REGISTER_DEBUGGER structure"]
ms.keywords: "*PPEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER structure [Kernel-Mode Driver Architecture], PPEP_REGISTER_DEBUGGER, PPEP_REGISTER_DEBUGGER structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_DEBUGGER, kernel.pep_register_debugger, pepfx/PEP_REGISTER_DEBUGGER, pepfx/PPEP_REGISTER_DEBUGGER"
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
req.typenames: PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER
f1_keywords:
 - _PEP_REGISTER_DEBUGGER
 - pep_x/_PEP_REGISTER_DEBUGGER
 - PPEP_REGISTER_DEBUGGER
 - pep_x/PPEP_REGISTER_DEBUGGER
 - PEP_REGISTER_DEBUGGER
 - pep_x/PEP_REGISTER_DEBUGGER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - _PEP_REGISTER_DEBUGGER
 - PPEP_REGISTER_DEBUGGER
 - PEP_REGISTER_DEBUGGER
---

# _PEP_REGISTER_DEBUGGER structure (pep_x.h)


## -description

The <b>PEP_REGISTER_DEBUGGER</b> structure identifies a registered device that is a core system resource that provides debugger transport.

## -struct-fields

### -field DeviceHandle

[in] A <b>PEPHANDLE</b> value that identifies the device. The PEP supplied this handle in response to a previous <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="/windows-hardware/drivers/ddi/_kernel/#device-power-management">power management framework</a> (PoFx).

## -see-also

<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a>



<a href="/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>


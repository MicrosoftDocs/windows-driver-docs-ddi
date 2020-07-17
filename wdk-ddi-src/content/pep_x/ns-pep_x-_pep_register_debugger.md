---
UID: NS:pep_x._PEP_REGISTER_DEBUGGER
title: _PEP_REGISTER_DEBUGGER (pep_x.h)
description: The PEP_REGISTER_DEBUGGER structure identifies a registered device that is a core system resource that provides debugger transport.
old-location: kernel\pep_register_debugger.htm
tech.root: kernel
ms.assetid: 3B0240AB-4599-4F21-8CBB-14A4A60D3EFD
ms.date: 04/30/2018
keywords: ["_PEP_REGISTER_DEBUGGER structure"]
ms.keywords: "*PPEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER, PEP_REGISTER_DEBUGGER structure [Kernel-Mode Driver Architecture], PPEP_REGISTER_DEBUGGER, PPEP_REGISTER_DEBUGGER structure pointer [Kernel-Mode Driver Architecture], _PEP_REGISTER_DEBUGGER, kernel.pep_register_debugger, pepfx/PEP_REGISTER_DEBUGGER, pepfx/PPEP_REGISTER_DEBUGGER"
f1_keywords:
 - "pep_x/PEP_REGISTER_DEBUGGER"
 - "PEP_REGISTER_DEBUGGER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_REGISTER_DEBUGGER
product:
- Windows
targetos: Windows
req.typenames: PEP_REGISTER_DEBUGGER, *PPEP_REGISTER_DEBUGGER
---

# _PEP_REGISTER_DEBUGGER structure


## -description


The <b>PEP_REGISTER_DEBUGGER</b> structure identifies a registered device that is a core system resource that provides debugger transport.


## -struct-fields




### -field DeviceHandle

[in] A <b>PEPHANDLE</b> value that identifies the device. The PEP supplied this handle in response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a> notification. The <b>DeviceHandle</b> member contains an input value that is supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_debugger">PEP_DPM_REGISTER_DEBUGGER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>
 

 


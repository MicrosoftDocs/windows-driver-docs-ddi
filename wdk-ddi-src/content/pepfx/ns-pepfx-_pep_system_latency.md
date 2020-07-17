---
UID: NS:pepfx._PEP_SYSTEM_LATENCY
title: _PEP_SYSTEM_LATENCY (pepfx.h)
description: The PEP_SYSTEM_LATENCY structure specifies the new value for the system latency tolerance.
old-location: kernel\pep_system_latency.htm
tech.root: kernel
ms.assetid: 083ACFD8-A8AE-4205-9E25-497D6A3ADBCD
ms.date: 04/30/2018
keywords: ["_PEP_SYSTEM_LATENCY structure"]
ms.keywords: "*PPEP_SYSTEM_LATENCY, PEP_SYSTEM_LATENCY, PEP_SYSTEM_LATENCY structure [Kernel-Mode Driver Architecture], PPEP_SYSTEM_LATENCY, PPEP_SYSTEM_LATENCY structure pointer [Kernel-Mode Driver Architecture], _PEP_SYSTEM_LATENCY, kernel.pep_system_latency, pepfx/PEP_SYSTEM_LATENCY, pepfx/PPEP_SYSTEM_LATENCY"
f1_keywords:
 - "pepfx/PEP_SYSTEM_LATENCY"
 - "PEP_SYSTEM_LATENCY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_SYSTEM_LATENCY
product:
- Windows
targetos: Windows
req.typenames: PEP_SYSTEM_LATENCY, *PPEP_SYSTEM_LATENCY
---

# _PEP_SYSTEM_LATENCY structure


## -description


The <b>PEP_SYSTEM_LATENCY</b> structure specifies the new value for the system latency tolerance.


## -struct-fields




### -field Latency

[in] The overall system latency tolerance, in 100-nanosecond units. This member specifies the maximum latency that the operating system can tolerate in the time required to move a component from a low-power F<i>x</i> state to F0.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_system_latency">PEP_DPM_SYSTEM_LATENCY_UPDATE</a> notification. The <b>Latency</b> member of the structure contains an input value that is supplied by the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">power management framework</a> (PoFx).




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_system_latency">PEP_DPM_SYSTEM_LATENCY_UPDATE</a>
 

 


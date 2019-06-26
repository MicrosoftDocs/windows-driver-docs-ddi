---
UID: NS:pepfx._PEP_PPM_IS_PROCESSOR_HALTED
title: _PEP_PPM_IS_PROCESSOR_HALTED (pepfx.h)
description: The PEP_PPM_IS_PROCESSOR_HALTED structure indicates whether the processor is currently halted in its selected idle state.
old-location: kernel\pep_ppm_is_processor_halted.htm
tech.root: kernel
ms.assetid: 284BAFE1-C632-428D-800C-60C538052C02
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_IS_PROCESSOR_HALTED, PEP_PPM_IS_PROCESSOR_HALTED, PEP_PPM_IS_PROCESSOR_HALTED structure [Kernel-Mode Driver Architecture], PPEP_PPM_IS_PROCESSOR_HALTED, PPEP_PPM_IS_PROCESSOR_HALTED structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_IS_PROCESSOR_HALTED, kernel.pep_ppm_is_processor_halted, pepfx/PEP_PPM_IS_PROCESSOR_HALTED, pepfx/PPEP_PPM_IS_PROCESSOR_HALTED"
ms.topic: struct
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
- PEP_PPM_IS_PROCESSOR_HALTED
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_IS_PROCESSOR_HALTED, *PPEP_PPM_IS_PROCESSOR_HALTED
---

# _PEP_PPM_IS_PROCESSOR_HALTED structure


## -description


The <b>PEP_PPM_IS_PROCESSOR_HALTED</b> structure indicates whether the processor is currently halted in its selected idle state.


## -struct-fields




### -field Halted

[out] Whether the processor is halted. Set to <b>TRUE</b> if the processor is halted, or to <b>FALSE</b> if it is not halted.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_is_processor_halted">PEP_NOTIFY_PPM_IS_PROCESSOR_HALTED</a> notification. The <b>Halted</b> member contains an output value that the platform extension plug-in (PEP) writes to the structure in response to this notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_is_processor_halted">PEP_NOTIFY_PPM_IS_PROCESSOR_HALTED</a>
 

 


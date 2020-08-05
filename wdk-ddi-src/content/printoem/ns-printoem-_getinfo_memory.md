---
UID: NS:printoem._GETINFO_MEMORY
title: _GETINFO_MEMORY (printoem.h)
description: The GETINFO_MEMORY structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_memory.htm
tech.root: print
ms.assetid: d6730599-a8f0-4bea-9ee4-47a60249271d
ms.date: 04/20/2018
keywords: ["GETINFO_MEMORY structure"]
ms.keywords: GETINFO_MEMORY, GETINFO_MEMORY structure [Print Devices], PGETINFO_MEMORY, PGETINFO_MEMORY structure pointer [Print Devices], PGETINFO_MEMROY, _GETINFO_MEMORY, print.getinfo_memory, print_unidrv-pscript_rendering_d39a4f36-c521-4da4-8f63-5121b344d33a.xml, printoem/GETINFO_MEMORY, printoem/PGETINFO_MEMORY
f1_keywords:
 - "printoem/GETINFO_MEMORY"
 - "GETINFO_MEMORY"
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
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
- printoem.h
api_name:
- GETINFO_MEMORY
targetos: Windows
req.typenames: GETINFO_MEMORY, PGETINFO_MEMROY
---

# _GETINFO_MEMORY structure


## -description


The GETINFO_MEMORY structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_MEMORY structure. Supplied by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> caller.


### -field dwRemainingMemory

Specifies the amount, in bytes, of currently available printer memory. Supplied by Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.


## -remarks



To obtain Unidrv's calculation of the amount of printer memory currently available, a rendering plug-in can supply the address of a GETINFO_MEMORY structure when calling Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>
 

 


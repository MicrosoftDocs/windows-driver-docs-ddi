---
UID: NS:printoem._GETINFO_MEMORY
title: GETINFO_MEMORY (printoem.h)
description: The GETINFO_MEMORY structure is used as input to the UNIFONTOBJ_GetInfo callback function.
tech.root: print
ms.date: 08/12/2022
keywords: ["GETINFO_MEMORY structure"]
ms.keywords: GETINFO_MEMORY, GETINFO_MEMORY structure [Print Devices], PGETINFO_MEMORY, PGETINFO_MEMORY structure pointer [Print Devices], PGETINFO_MEMROY, _GETINFO_MEMORY, print.getinfo_memory, print_unidrv-pscript_rendering_d39a4f36-c521-4da4-8f63-5121b344d33a.xml, printoem/GETINFO_MEMORY, printoem/PGETINFO_MEMORY
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
targetos: Windows
req.typenames: GETINFO_MEMORY, PGETINFO_MEMROY
f1_keywords:
 - _GETINFO_MEMORY
 - printoem/_GETINFO_MEMORY
 - GETINFO_MEMORY
 - printoem/GETINFO_MEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _GETINFO_MEMORY
 - GETINFO_MEMORY
---

## -description

The **GETINFO_MEMORY** structure is used as input to the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the **GETINFO_MEMORY** structure. Supplied by the [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) caller.

### -field dwRemainingMemory

Specifies the amount, in bytes, of currently available printer memory. Supplied by Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -remarks

To obtain Unidrv's calculation of the amount of printer memory currently available, a rendering plug-in can supply the address of a **GETINFO_MEMORY** structure when calling Unidrv's [UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md) callback function.

## -see-also

[UNIFONTOBJ_GetInfo](./nc-printoem-pfngetinfo.md)
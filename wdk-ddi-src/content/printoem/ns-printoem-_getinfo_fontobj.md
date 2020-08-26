---
UID: NS:printoem._GETINFO_FONTOBJ
title: _GETINFO_FONTOBJ (printoem.h)
description: The GETINFO_FONTOBJ structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_fontobj.htm
tech.root: print
ms.assetid: f5116986-aa0c-4cc3-9893-c93e83e922f7
ms.date: 04/20/2018
keywords: ["GETINFO_FONTOBJ structure"]
ms.keywords: "*PGETINFO_FONTOBJ, GETINFO_FONTOBJ, GETINFO_FONTOBJ structure [Print Devices], PGETINFO_FONTOBJ, PGETINFO_FONTOBJ structure pointer [Print Devices], _GETINFO_FONTOBJ, print.getinfo_fontobj, print_unidrv-pscript_rendering_2fdbe41f-95af-46ef-be82-04c1dc02297f.xml, printoem/GETINFO_FONTOBJ, printoem/PGETINFO_FONTOBJ"
f1_keywords:
 - "printoem/GETINFO_FONTOBJ"
 - "GETINFO_FONTOBJ"
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
- GETINFO_FONTOBJ
targetos: Windows
req.typenames: GETINFO_FONTOBJ, *PGETINFO_FONTOBJ
---

# _GETINFO_FONTOBJ structure


## -description


The GETINFO_FONTOBJ structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_FONTOBJ structure. Supplied by the UNIFONTOBJ_GetInfo caller.


### -field pFontObj

Pointer to an empty <a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_fontobj">FONTOBJ</a> structure. The structure is filled in by Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function. The pointer is supplied by the UNIFONTOBJ_GetInfo caller.


## -remarks



To obtain a font's FONTOBJ structure contents, a rendering plug-in can supply the address of a GETINFO_FONTOBJ structure when calling Unidrv's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a> callback function.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/winddi/ns-winddi-_fontobj">FONTOBJ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/nc-printoem-pfngetinfo">UNIFONTOBJ_GetInfo</a>
 

 


---
UID: NS:printoem._GETINFO_GLYPHBITMAP
title: "_GETINFO_GLYPHBITMAP"
description: The GETINFO_GLYPHBITMAP structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphbitmap.htm
tech.root: print
ms.assetid: 6a5887fd-0269-4cd1-acf1-f7242016d993
ms.date: 04/20/2018
ms.keywords: "*PGETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP, GETINFO_GLYPHBITMAP structure [Print Devices], PGETINFO_GLYPHBITMAP, PGETINFO_GLYPHBITMAP structure pointer [Print Devices], _GETINFO_GLYPHBITMAP, print.getinfo_glyphbitmap, print_unidrv-pscript_rendering_56355138-13b0-4e8b-8132-f7c017105ab3.xml, printoem/GETINFO_GLYPHBITMAP, printoem/PGETINFO_GLYPHBITMAP"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	GETINFO_GLYPHBITMAP
product:
- Windows
targetos: Windows
req.typenames: GETINFO_GLYPHBITMAP, *PGETINFO_GLYPHBITMAP
---

# _GETINFO_GLYPHBITMAP structure


## -description


The GETINFO_GLYPHBITMAP structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Specifies the size, in bytes, of the GETINFO_GLYPHBITMAP structure. Supplied by <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field hGlyph

Handle to the glyph. See the following Remarks section. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field pGlyphData

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff566819">GLYPHDATA</a> structure. The structure is filled in by Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. The pointer is supplied by the <i>UNIFONTOBJ_GetInfo</i> caller.


## -remarks



To obtain a glyph bitmap, a rendering plug-in can supply the address of a GETINFO_GLYPHBITMAP structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.

The value that a rendering plug-in specifies for the <b>hGlyph</b> member must have been previously received as the <i>hGlyph</i> parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554241">IPrintOemUni::DownloadCharGlyph</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566819">GLYPHDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554241">IPrintOemUni::DownloadCharGlyph</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
 

 


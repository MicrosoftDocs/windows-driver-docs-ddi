---
UID: NS:printoem._GETINFO_GLYPHWIDTH
title: "_GETINFO_GLYPHWIDTH"
author: windows-driver-content
description: The GETINFO_GLYPHWIDTH structure is used as input to the UNIFONTOBJ_GetInfo callback function.
old-location: print\getinfo_glyphwidth.htm
old-project: print
ms.assetid: bc01b363-71e9-4c50-ad14-a101abbfe6ec
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGETINFO_GLYPHWIDTH, GETINFO_GLYPHWIDTH, GETINFO_GLYPHWIDTH structure [Print Devices], PGETINFO_GLYPHWIDTH, PGETINFO_GLYPHWIDTH structure pointer [Print Devices], _GETINFO_GLYPHWIDTH, print.getinfo_glyphwidth, print_unidrv-pscript_rendering_d4e07803-7342-4550-90fd-1ee8669934f0.xml, printoem/GETINFO_GLYPHWIDTH, printoem/PGETINFO_GLYPHWIDTH"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	GETINFO_GLYPHWIDTH
product: Windows
targetos: Windows
req.typenames: GETINFO_GLYPHWIDTH, *PGETINFO_GLYPHWIDTH
req.product: Windows 10 or later.
---

# _GETINFO_GLYPHWIDTH structure


## -description


The GETINFO_GLYPHWIDTH structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function.


## -struct-fields




### -field dwSize

Size, in bytes, of the GETINFO_GLYPHWIDTH structure. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field dwType

Specifies the type of the glyph specifier array pointed to by <b>pGlyph</b>. Valid values are:

TYPE_GLYPHHANDLE

TYPE_GLYPHID

Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field dwCount

Specifies the number of elements in the array pointed to by <b>pGlyph</b>. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field pGlyph

Pointer to an array of glyph specifiers. The array element type is indicated by <b>dwType</b>. Supplied by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> caller.


### -field plWidth

Pointer to a location into which Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function places the width value. The pointer is supplied by the <i>UNIFONTOBJ_GetInfo</i> caller.


## -remarks



To obtain the width of a set of glyphs, a rendering plug-in can supply the address of a GETINFO_GLYPHWIDTH structure when calling Unidrv's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a> callback function. The callback function calculates the total width of all the glyphs described by the input array, and places the calculated value in the location pointed to by <b>plWidth</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563594">UNIFONTOBJ_GetInfo</a>
 

 


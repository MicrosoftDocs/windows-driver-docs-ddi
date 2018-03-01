---
UID: NS:prntfont._GLYPHRUN
title: "_GLYPHRUN"
author: windows-driver-content
description: The GLYPHRUN structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\glyphrun.htm
old-project: print
ms.assetid: 21f6631c-dff1-459f-a83e-7aa1d5d2ab2b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PGLYPHRUN, GLYPHRUN, GLYPHRUN structure [Print Devices], PGLYPHRUN, PGLYPHRUN structure pointer [Print Devices], _GLYPHRUN, print.glyphrun, print_unidrv-pscript_fonts_591184a3-96f1-4b27-bf6a-d1c512a2bf7e.xml, prntfont/GLYPHRUN, prntfont/PGLYPHRUN"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
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
-	prntfont.h
api_name:
-	GLYPHRUN
product: Windows
targetos: Windows
req.typenames: GLYPHRUN, *PGLYPHRUN
req.product: Windows 10 or later.
---

# _GLYPHRUN structure


## -description


The GLYPHRUN structure is one of the structures used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).


## -syntax


````
typedef struct _GLYPHRUN {
  WCHAR wcLow;
  WORD  wGlyphCount;
} GLYPHRUN, *PGLYPHRUN;
````


## -struct-fields




### -field wcLow

Specifies a Unicode value representing the first glyph in the glyph run.


### -field wGlyphCount

Specifies the number of glyphs represented by the glyph run.


## -remarks



A .gtt (glyph translation table) file contains an array of GLYPHRUN structures. Each structure identifies a set of Unicode values for which the printer provides glyphs. The array is described by the <b>IoRunOffset</b> and <b>dwRunCount</b> members of a .gtt file's <a href="..\prntfont\ns-prntfont-_uni_glyphsetdata.md">UNI_GLYPHSETDATA</a> structure.

The GLYPHRUN structures must be defined in ascending order, based on the value of <b>wcLow</b>. Unidrv uses the GLYPHRUN array to generate glyph handles. Unidrv stores these glyph handles in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570578">WCRUN</a> array within an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565625">FD_GLYPHSET</a> structure.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570578">WCRUN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565625">FD_GLYPHSET</a>



<a href="..\prntfont\ns-prntfont-_uni_glyphsetdata.md">UNI_GLYPHSETDATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GLYPHRUN structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


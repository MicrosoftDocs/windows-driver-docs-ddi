---
UID: NS:prntfont._UNI_GLYPHSETDATA
title: "_UNI_GLYPHSETDATA" (prntfont.h)
description: The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\uni_glyphsetdata.htm
tech.root: print
ms.assetid: a2c98783-c463-435e-9d78-c10686f1c75c
ms.date: 04/20/2018
ms.keywords: "*PUNI_GLYPHSETDATA, PUNI_GLYPHSETDATA, PUNI_GLYPHSETDATA structure pointer [Print Devices], UNI_GLYPHSETDATA, UNI_GLYPHSETDATA structure [Print Devices], _UNI_GLYPHSETDATA, print.uni_glyphsetdata, print_unidrv-pscript_fonts_51c5f97c-3b3c-4990-8dcb-9c7bf387b03f.xml, prntfont/PUNI_GLYPHSETDATA, prntfont/UNI_GLYPHSETDATA"
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
-	UNI_GLYPHSETDATA
product:
- Windows
targetos: Windows
req.typenames: UNI_GLYPHSETDATA, *PUNI_GLYPHSETDATA
---

# _UNI_GLYPHSETDATA structure


## -description


The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).


## -struct-fields




### -field dwSize

Specifies the total size, in bytes, of the .gtt file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNI_GLYPHSETDATA structure.


### -field dwVersion

Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNI_GLYPHSETDATA_VERSION_<i>x</i>_<i>x</i>.


### -field dwFlags

Not used.


### -field lPredefinedID

Specifies one of the CC_-prefixed code conversion identifiers defined in prntfont.h. 


### -field dwGlyphCount

Specifies the number of glyphs provided by this font.


### -field dwRunCount

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550544">GLYPHRUN</a> structures in the array pointed to by <b>loRunOffset</b>.


### -field loRunOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff550544">GLYPHRUN</a> structures.


### -field dwCodePageCount

Specifies the number of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563596">UNI_CODEPAGEINFO</a> structures in the array pointed to by <b>loCodePageOffset</b>.


### -field loCodePageOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563596">UNI_CODEPAGEINFO</a> structures.


### -field loMapTableOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff556509">MAPTABLE</a> structure.


### -field dwReserved

Reserved for system use.


## -remarks



A UNI_GLYPHSETDATA structure must be the first structure contained in a .gtt file.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550544">GLYPHRUN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556509">MAPTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563596">UNI_CODEPAGEINFO</a>
 

 


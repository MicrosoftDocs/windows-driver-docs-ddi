---
UID: NS:prntfont._MAPTABLE
title: "_MAPTABLE"
author: windows-driver-content
description: The MAPTABLE structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\maptable.htm
old-project: print
ms.assetid: d3dcf7b0-4244-41c1-801e-cf41b20f2d54
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_unidrv-pscript_fonts_c98fd60e-c56a-4f76-8408-e6680bc49525.xml, *PMAPTABLE, MAPTABLE structure [Print Devices], PMAPTABLE structure pointer [Print Devices], MAPTABLE, prntfont/MAPTABLE, _MAPTABLE, print.maptable, prntfont/PMAPTABLE, PMAPTABLE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	prntfont.h
apiname:
-	MAPTABLE
product: Windows
targetos: Windows
req.typenames: "*PMAPTABLE, MAPTABLE"
req.product: Windows 10 or later.
---

# _MAPTABLE structure


## -description


The MAPTABLE structure is one of the structures used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).


## -syntax


````
typedef struct _MAPTABLE {
  DWORD     dwSize;
  DWORD     dwGlyphNum;
  TRANSDATA Trans[1];
} MAPTABLE, *PMAPTABLE;
````


## -struct-fields




#### - dwSize

Specifies the size, in bytes, of the MAPTABLE structure, including the <b>Trans</b> array.


#### - dwGlyphNum

Specifies the number of elements in the <b>Trans</b> array.


#### - Trans

Is an array of <a href="..\prntfont\ns-prntfont-_transdata.md">TRANSDATA</a> structures.


## -remarks


A .gtt file's MAPTABLE structure, which contains a glyph mapping table, is accessed by a pointer in the file's <a href="..\prntfont\ns-prntfont-_uni_glyphsetdata.md">UNI_GLYPHSETDATA</a> structure. The table maps glyph handles to the character codes or commands that must be sent to the printer in order to print glyphs.



## -see-also

<a href="..\prntfont\ns-prntfont-_transdata.md">TRANSDATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MAPTABLE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


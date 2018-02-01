---
UID: NS:prntfont._UFF_FILEHEADER
title: "_UFF_FILEHEADER"
author: windows-driver-content
description: The UFF_FILEHEADER structure is used to define the contents of Unidrv font format files (.uff files).
old-location: print\uff_fileheader.htm
old-project: print
ms.assetid: 18eb526b-d615-4f02-b724-236c6bf16945
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "_UFF_FILEHEADER, print.uff_fileheader, UFF_FILEHEADER structure [Print Devices], *PUFF_FILEHEADER, PUFF_FILEHEADER structure pointer [Print Devices], prntfont/PUFF_FILEHEADER, prntfont/UFF_FILEHEADER, print_unidrv-pscript_fonts_a51bc6b1-df89-423f-83e8-9fad0cd20729.xml, PUFF_FILEHEADER, UFF_FILEHEADER"
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
-	UFF_FILEHEADER
product: Windows
targetos: Windows
req.typenames: "*PUFF_FILEHEADER, UFF_FILEHEADER"
req.product: Windows 10 or later.
---

# _UFF_FILEHEADER structure


## -description


The UFF_FILEHEADER structure is used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font format files</a> (.uff files).


## -syntax


````
typedef struct _UFF_FILEHEADER {
  DWORD dwSignature;
  DWORD dwVersion;
  DWORD dwSize;
  DWORD nFonts;
  DWORD nGlyphSets;
  DWORD nVarData;
  DWORD offFontDir;
  DWORD dwFlags;
  DWORD dwReserved[4];
} UFF_FILEHEADER, *PUFF_FILEHEADER;
````


## -struct-fields




### -field dwSignature

Specifies the signature for .uff files. This value must be UFF_FILE_MAGIC.


### -field dwVersion

Specifies the format version for .uff files. This value must be UFF_VERSION_NUMBER. The HIWORD contains the major version number and the LOWORD contains the minor version number.


### -field dwSize

Specifies the size, in bytes, of the UFF_FILEHEADER structure.


### -field nFonts

Specifies the number of fonts specified within the .uff file and identified by <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structures. This is also the number of <a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a> structures within the .uff file.


### -field nGlyphSets

Specifies the  number of glyph sets specified within the .uff file and identified by DATA_HEADER structures. Some fonts might share a glyph set.


### -field nVarData

Specifies the  number of variable data sections specified within the .uff file and identified by DATA_HEADER structures.


### -field offFontDir

Specifies the offset, in bytes, from the beginning of the .uff file to the beginning of the first <a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a> structure.


### -field dwFlags

Is a set of bit flags, as specified in the following table.
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
FONT_DIR_SORTED

</td>
<td>
The array of UFF_FONTDIRECTORY structures (specified by <b>offFontDir</b>) is sorted by the contents of that structure's <b>wFontID</b> member.

</td>
</tr>
</table> 


### -field dwReserved

Reserved. Must be set to zero.


## -see-also

<a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a>

<a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UFF_FILEHEADER structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


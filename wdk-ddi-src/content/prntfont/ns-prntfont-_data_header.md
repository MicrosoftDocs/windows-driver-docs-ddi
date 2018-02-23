---
UID: NS:prntfont._DATA_HEADER
title: "_DATA_HEADER"
author: windows-driver-content
description: The DATA_HEADER structure is used to specify a data section within a Unidrv font format file (.uff file).
old-location: print\data_header.htm
old-project: print
ms.assetid: 8c7b6d2f-d2d9-49a5-8137-13d71dfd2611
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: PDATA_HEADER structure pointer [Print Devices], PDATA_HEADER, *PDATA_HEADER, prntfont/PDATA_HEADER, _DATA_HEADER, DATA_HEADER structure [Print Devices], print_unidrv-pscript_fonts_7b54b761-a2d8-419d-9726-628cfd33dae6.xml, prntfont/DATA_HEADER, DATA_HEADER, print.data_header
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
-	DATA_HEADER
product: Windows
targetos: Windows
req.typenames: "*PDATA_HEADER, DATA_HEADER"
req.product: Windows 10 or later.
---

# _DATA_HEADER structure


## -description


The DATA_HEADER structure is used to specify a data section within a Unidrv font format file (.uff file).


## -syntax


````
typedef struct _DATA_HEADER {
  DWORD dwSignature;
  WORD  wSize;
  WORD  wDataID;
  DWORD dwDataSize;
  DWORD dwReserved;
} DATA_HEADER, *PDATA_HEADER;
````


## -struct-fields




### -field dwSignature

Specifies the signature value identifying the type of data in the data section. Valid signature values are listed in the following table.

<table>
<tr>
<th>Signature</th>
<th>Definition</th>
</tr>
<tr>
<td>
DATA_CTT_SIG

</td>
<td>
This data section contains <a href="https://msdn.microsoft.com/ac439eb8-b491-4215-877d-5ee177fbdb39">CTT</a>-formatted glyph set information.

</td>
</tr>
<tr>
<td>
DATA_GTT_SIG

</td>
<td>
This data section contains <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GTT</a>-formatted glyph set information.

</td>
</tr>
<tr>
<td>
DATA_IFI_SIG

</td>
<td>
This data section contains IFI-formatted font metrics.

</td>
</tr>
<tr>
<td>
DATA_UFM_SIG

</td>
<td>
This data section contains <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">UFM</a>-formatted font metrics.

</td>
</tr>
<tr>
<td>
DATA_VAR_SIG

</td>
<td>
This data section contains data to be downloaded to the printer. See the following Remarks section.

</td>
</tr>
</table>
 


### -field wSize

Specifies the size, in bytes, of the DATA_HEADER structure.


### -field wDataID

If the data section contains font metrics data, this value must be a unique font identifier. For fonts that are permanently downloaded by the font installer, this value should be the downloaded font's identifier.

If the data section contains glyph data, this value must be a glyph set identifier.

If the data section contains variable data, this value must be zero.


### -field dwDataSize

Specifies the size, in bytes, of all the information represented by this DATA_HEADER structure. For example, if <b>dwSignature</b> is DATA_UFM_SIG, this value represents the size, in bytes, of the font's <a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a> structure and all associated structures. The size value does not include any byte padding required to align the next DATA_HEADER structure to a DWORD.


### -field dwReserved

Not used. Must be set to zero.


## -remarks



If <b>dwSignature</b> is DATA_VAR_SIG, the data section contains variable data that Unidrv sends to the printer the first time the font is selected. Typically, this data consists of a font header and corresponding font identifier, along with downloadable glyph information for all the glyphs supported by the font. <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PCL</a> soft font information includes printer control language commands for loading the font header and glyph definitions for all supported glyphs. Unidrv does not validate variable data. Data validation should be performed by the font installer.

Each DATA_HEADER structure must be DWORD-aligned.




## -see-also

<a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DATA_HEADER structure%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


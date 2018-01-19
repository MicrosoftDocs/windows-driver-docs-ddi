---
UID: NS:prntfont._DATA_HEADER
title: _DATA_HEADER
author: windows-driver-content
description: The DATA_HEADER structure is used to specify a data section within a Unidrv font format file (.uff file).
old-location: print\data_header.htm
old-project: print
ms.assetid: 8c7b6d2f-d2d9-49a5-8137-13d71dfd2611
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DATA_HEADER, DATA_HEADER, *PDATA_HEADER
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
req.alt-api: DATA_HEADER
req.alt-loc: prntfont.h
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
req.typenames: DATA_HEADER, *PDATA_HEADER
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
This data section contains <a href="wdkgloss.c#wdkgloss.character_translation_table__ctt_#wdkgloss.character_translation_table__ctt_"><i>CTT</i></a>-formatted glyph set information.

</td>
</tr>
<tr>
<td>
DATA_GTT_SIG

</td>
<td>
This data section contains <a href="wdkgloss.g#wdkgloss.glyph_translation_table__gtt_#wdkgloss.glyph_translation_table__gtt_"><i>GTT</i></a>-formatted glyph set information.

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
This data section contains <a href="wdkgloss.u#wdkgloss.unidrv_font_metrics__ufm_#wdkgloss.unidrv_font_metrics__ufm_"><i>UFM</i></a>-formatted font metrics.

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
If <b>dwSignature</b> is DATA_VAR_SIG, the data section contains variable data that Unidrv sends to the printer the first time the font is selected. Typically, this data consists of a font header and corresponding font identifier, along with downloadable glyph information for all the glyphs supported by the font. <a href="wdkgloss.p#wdkgloss.pcl#wdkgloss.pcl"><i>PCL</i></a> soft font information includes printer control language commands for loading the font header and glyph definitions for all supported glyphs. Unidrv does not validate variable data. Data validation should be performed by the font installer.

Each DATA_HEADER structure must be DWORD-aligned.


## -see-also
<dl>
<dt>
<a href="..\prntfont\ns-prntfont-_unifm_hdr.md">UNIFM_HDR</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20DATA_HEADER structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


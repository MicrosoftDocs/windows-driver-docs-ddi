---
UID: NS:prntfont._UNIFM_HDR
title: "_UNIFM_HDR"
author: windows-driver-content
description: The UNIFM_HDR structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\unifm_hdr.htm
old-project: print
ms.assetid: 9490d090-2156-4653-9e56-a233d23c2fb3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUNIFM_HDR, PUNIFM_HDR, PUNIFM_HDR structure pointer [Print Devices], UNIFM_HDR, UNIFM_HDR structure [Print Devices], _UNIFM_HDR, print.unifm_hdr, print_unidrv-pscript_fonts_eaf5dd18-df64-41bc-91b5-836b6ed165b6.xml, prntfont/PUNIFM_HDR, prntfont/UNIFM_HDR"
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
-	UNIFM_HDR
product: Windows
targetos: Windows
req.typenames: UNIFM_HDR, *PUNIFM_HDR
req.product: Windows 10 or later.
---

# _UNIFM_HDR structure


## -description


The UNIFM_HDR structure is used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font metrics files</a> (.ufm files).


## -syntax


````
typedef struct _UNIFM_HDR {
  DWORD dwSize;
  DWORD dwVersion;
  ULONG ulDefaultCodepage;
  LONG  lGlyphSetDataRCID;
  DWORD loUnidrvInfo;
  DWORD loIFIMetrics;
  DWORD loExtTextMetric;
  DWORD loWidthTable;
  DWORD loKernPair;
  DWORD dwReserved[2];
} UNIFM_HDR, *PUNIFM_HDR;
````


## -struct-fields




### -field dwSize

Specifies the total size, in bytes, of the .ufm file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNIFM_HDR structure.


### -field dwVersion

Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNIFM_VERSION_<i>x</i>_<i>x</i>.


### -field ulDefaultCodepage

Specifies the code page identifier for the font's default code page. For more information, see the following Remarks section.


### -field lGlyphSetDataRCID

Specifies an RC_GTT resource identifier that identifies a .gtt (Glyph Translation Table) file, or one of the CC_-prefixed code conversion identifiers defined in prntfont.h. For more information, see the following Remarks section.


### -field loUnidrvInfo

Specifies the byte offset from the beginning of the .ufm (Unidrv Font Metrics) file to the location of the file's <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structure.


### -field loIFIMetrics

Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont-_printifi32.md">PRINTIFI32</a> structure.


### -field loExtTextMetric

Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont-_exttextmetric.md">EXTTEXTMETRIC</a> structure.


### -field loWidthTable

Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont-_widthtable.md">WIDTHTABLE</a> structure.


### -field loKernPair

Specifies the byte offset from the beginning of the .ufm file to the location of the file's <a href="..\prntfont\ns-prntfont-_kerndata.md">KERNDATA</a> structure.


### -field dwReserved

Not used.


## -remarks



A UNIFM_HDR structure must be the first structure contained in a .ufm file.

If <b>lGlyphSetDataRCID</b> is not CC_DEFAULT, then the following rules apply:

<ul>
<li>
If <b>lGlyphSetDataRCID</b> contains an RC_GTT resource identifier, the code page number specified for <b>ulDefaultCodepage</b> must be the same code page number that is contained in the .gtt (Glyph Translation Table) file's first <a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a> structure.

</li>
<li>
If <b>lGlyphSetDataRCID</b> contains one of the CC_-prefixed code conversion identifiers (other than CC_DEFAULT), the code page number specified for <b>ulDefaultCodepage</b> must be the code page number that is associated with the CC_-prefixed identifier. (These code page numbers are listed in Prntfont.h, next to each CC_-prefixed identifier.)

The character conversion codes predefined by the system, listed in Prntfont.h, are as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// System predefined character conversion
//
// UNIDRV is going to support  following system predefined character conversion.
// By speciffying these number in UNIFM.dwGlyphSetDataRCID;
//

#define CC_NOPRECNV 0x0000FFFF // Not use predefined

//
// ANSI
//
#define CC_DEFAULT  0 // Default Character Conversion
#define CC_CP437   -1 // Unicode to IBM Codepage 437
#define CC_CP850   -2 // Unicode to IBM Codepage 850
#define CC_CP863   -3 // Unicode to IBM Codepage 863

//
// East Asia
//

#define CC_BIG5     -10 // Unicode to Chinese Big 5. Codepage 950.
#define CC_ISC      -11 // Unicode to Korean Industrial Standard. Codepage 949.
#define CC_JIS      -12 // Unicode to JIS X0208. Codepage 932.
#define CC_JIS_ANK  -13 // Unicode to JIS X0208 except ANK. Codepage 932.
#define CC_NS86     -14 // Big-5 to National Standstand conversion. Codepage 950
#define CC_TCA      -15 // Big-5 to Taipei Computer Association. Codepage 950.
#define CC_GB2312   -16 // Unicode to GB2312. Codepage 936
#define CC_SJIS     -17 // Unicode to Shift-JIS. Codepage 932.
#define CC_WANSUNG  -18 // Unicode to Extented Wansung. Codepage 949.</pre>
</td>
</tr>
</table></span></div>
</li>
</ul>
If <b>lGlyphSetDataRCID</b> is CC_DEFAULT, there are no restrictions on the value specified for <b>ulDefaultCodepage</b>, but a default code page must be specified.




## -see-also

<a href="..\prntfont\ns-prntfont-_printifi32.md">PRINTIFI32</a>



<a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a>



<a href="..\prntfont\ns-prntfont-_exttextmetric.md">EXTTEXTMETRIC</a>



<a href="..\prntfont\ns-prntfont-_widthtable.md">WIDTHTABLE</a>



<a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a>



<a href="..\prntfont\ns-prntfont-_kerndata.md">KERNDATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNIFM_HDR structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


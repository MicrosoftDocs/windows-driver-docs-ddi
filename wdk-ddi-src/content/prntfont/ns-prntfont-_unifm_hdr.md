---
UID: NS:prntfont._UNIFM_HDR
title: _UNIFM_HDR (prntfont.h)
description: The UNIFM_HDR structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\unifm_hdr.htm
tech.root: print
ms.assetid: 9490d090-2156-4653-9e56-a233d23c2fb3
ms.date: 04/20/2018
ms.keywords: "*PUNIFM_HDR, PUNIFM_HDR, PUNIFM_HDR structure pointer [Print Devices], UNIFM_HDR, UNIFM_HDR structure [Print Devices], _UNIFM_HDR, print.unifm_hdr, print_unidrv-pscript_fonts_eaf5dd18-df64-41bc-91b5-836b6ed165b6.xml, prntfont/PUNIFM_HDR, prntfont/UNIFM_HDR"
f1_keywords:
 - "prntfont/UNIFM_HDR"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- prntfont.h
api_name:
- UNIFM_HDR
product:
- Windows
targetos: Windows
req.typenames: UNIFM_HDR, *PUNIFM_HDR
---

# _UNIFM_HDR structure

## -description

The UNIFM_HDR structure is used to define the contents of [Unidrv font metrics files](https://docs.microsoft.com/windows-hardware/drivers/print/customized-font-management) (.ufm files).

## -struct-fields

### -field dwSize

Specifies the total size, in bytes, of the .ufm file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNIFM_HDR structure.

### -field dwVersion

Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNIFM_VERSION_*x*_*x*.

### -field ulDefaultCodepage

Specifies the code page identifier for the font's default code page. For more information, see the following Remarks section.

### -field lGlyphSetDataRCID

Specifies an RC_GTT resource identifier that identifies a .gtt (Glyph Translation Table) file, or one of the CC_-prefixed code conversion identifiers defined in prntfont.h. For more information, see the following Remarks section.

### -field loUnidrvInfo

Specifies the byte offset from the beginning of the .ufm (Unidrv Font Metrics) file to the location of the file's [UNIDRVINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unidrvinfo) structure.

### -field loIFIMetrics

Specifies the byte offset from the beginning of the .ufm file to the location of the file's [PRINTIFI32](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_printifi32) structure.

### -field loExtTextMetric

Specifies the byte offset from the beginning of the .ufm file to the location of the file's [EXTTEXTMETRIC](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_exttextmetric) structure.

### -field loWidthTable

Specifies the byte offset from the beginning of the .ufm file to the location of the file's [WIDTHTABLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_widthtable) structure.

### -field loKernPair

Specifies the byte offset from the beginning of the .ufm file to the location of the file's [KERNDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_kerndata) structure.

### -field dwReserved

Not used.

## -remarks

A UNIFM_HDR structure must be the first structure contained in a .ufm file.

If **lGlyphSetDataRCID** is not CC_DEFAULT, then the following rules apply:

- If **lGlyphSetDataRCID** contains an RC_GTT resource identifier, the code page number specified for **ulDefaultCodepage** must be the same code page number that is contained in the .gtt (Glyph Translation Table) file's first [UNI_CODEPAGEINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_codepageinfo) structure.

- If **lGlyphSetDataRCID** contains one of the CC_-prefixed code conversion identifiers (other than CC_DEFAULT), the code page number specified for **ulDefaultCodepage** must be the code page number that is associated with the CC_-prefixed identifier. (These code page numbers are listed in Prntfont.h, next to each CC_-prefixed identifier.)

    The character conversion codes predefined by the system, listed in Prntfont.h, are as follows:

    ```cpp
    //
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
    #define CC_WANSUNG  -18 // Unicode to Extented Wansung. Codepage 949.
    ```

If **lGlyphSetDataRCID** is CC_DEFAULT, there are no restrictions on the value specified for **ulDefaultCodepage**, but a default code page must be specified.

## -see-also

[EXTTEXTMETRIC](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_exttextmetric)

[KERNDATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_kerndata)

[PRINTIFI32](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_printifi32)

[UNIDRVINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_unidrvinfo)

[UNI_CODEPAGEINFO](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_uni_codepageinfo)

[WIDTHTABLE](https://docs.microsoft.com/windows-hardware/drivers/ddi/prntfont/ns-prntfont-_widthtable)

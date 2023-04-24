---
UID: NS:prntfont._DATA_HEADER
title: _DATA_HEADER (prntfont.h)
description: The DATA_HEADER structure is used to specify a data section within a Unidrv font format file (.uff file).
tech.root: print
ms.date: 03/07/2023
keywords: ["DATA_HEADER structure"]
ms.keywords: "*PDATA_HEADER, DATA_HEADER, DATA_HEADER structure [Print Devices], PDATA_HEADER, PDATA_HEADER structure pointer [Print Devices], _DATA_HEADER, print.data_header, print_unidrv-pscript_fonts_7b54b761-a2d8-419d-9726-628cfd33dae6.xml, prntfont/DATA_HEADER, prntfont/PDATA_HEADER"
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
targetos: Windows
req.typenames: DATA_HEADER, *PDATA_HEADER
f1_keywords:
 - _DATA_HEADER
 - prntfont/_DATA_HEADER
 - PDATA_HEADER
 - prntfont/PDATA_HEADER
 - DATA_HEADER
 - prntfont/DATA_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - prntfont.h
api_name:
 - _DATA_HEADER
 - PDATA_HEADER
 - DATA_HEADER
---

## -description

The **DATA_HEADER** structure is used to specify a data section within a Unidrv font format file (.uff file).

## -struct-fields

### -field dwSignature

Specifies the signature value identifying the type of data in the data section. Valid signature values are listed in the following table.

| Signature | Definition |
|---|---|
| DATA_CTT_SIG | This data section contains [CTT](/windows-hardware/drivers/)-formatted glyph set information. |
| DATA_GTT_SIG | This data section contains [GTT](/windows-hardware/drivers/)-formatted glyph set information. |
| DATA_IFI_SIG | This data section contains IFI-formatted font metrics. |
| DATA_UFM_SIG | This data section contains [UFM](/windows-hardware/drivers/)-formatted font metrics. |
| DATA_VAR_SIG | This data section contains data to be downloaded to the printer. See the following Remarks section. |

### -field wSize

Specifies the size, in bytes, of the DATA_HEADER structure.

### -field wDataID

If the data section contains font metrics data, this value must be a unique font identifier. For fonts that are permanently downloaded by the font installer, this value should be the downloaded font's identifier.

If the data section contains glyph data, this value must be a glyph set identifier.

If the data section contains variable data, this value must be zero.

### -field dwDataSize

Specifies the size, in bytes, of all the information represented by this DATA_HEADER structure. For example, if **dwSignature** is DATA_UFM_SIG, this value represents the size, in bytes, of the font's [**UNIFM_HDR**](./ns-prntfont-_unifm_hdr.md) structure and all associated structures. The size value does not include any byte padding required to align the next DATA_HEADER structure to a DWORD.

### -field dwReserved

Not used. Must be set to zero.

## -remarks

If **dwSignature** is DATA_VAR_SIG, the data section contains variable data that Unidrv sends to the printer the first time the font is selected. Typically, this data consists of a font header and corresponding font identifier, along with downloadable glyph information for all the glyphs supported by the font. [PCL](/windows-hardware/drivers/) soft font information includes printer control language commands for loading the font header and glyph definitions for all supported glyphs. Unidrv does not validate variable data. Data validation should be performed by the font installer.

Each DATA_HEADER structure must be DWORD-aligned.

## -see-also

[**UNIFM_HDR**](./ns-prntfont-_unifm_hdr.md)
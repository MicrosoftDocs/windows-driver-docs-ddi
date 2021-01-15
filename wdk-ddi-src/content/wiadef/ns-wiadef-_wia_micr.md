---
UID: NS:wiadef._WIA_MICR
title: _WIA_MICR (wiadef.h)
description: The WIA_MICR structure stores header information for the MICR metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_micr.htm
tech.root: image
ms.date: 05/03/2018
keywords: ["WIA_MICR structure"]
ms.keywords: WIA_MICR, WIA_MICR structure [Imaging Devices], _WIA_MICR, image.wia_micr, wiadef/WIA_MICR
req.header: wiadef.h
req.include-header: Wiadef.h
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
req.typenames: WIA_MICR
f1_keywords:
 - _WIA_MICR
 - wiadef/_WIA_MICR
 - WIA_MICR
 - wiadef/WIA_MICR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wiadef.h
api_name:
 - _WIA_MICR
 - WIA_MICR
---

# _WIA_MICR structure


## -description

The <b>WIA_MICR</b> structure stores header information for the MICR metadata report of one scan job (one call to <a href="/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata">IWiaMiniDrv::drvAcquireItemData</a>).

## -struct-fields

### -field Tag

Must be the literal 'WMIC', 4 single byte ASCII characters.

### -field Version

Must be the value 0x00010000 (Version 1.0).

### -field Size

The complete size of this <b>WIA_MICR</b> header structure, in bytes, including the complete size of the <a href="/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_micr_info">WIA_MICR_INFO</a> list.

### -field Placeholder

Placeholder for unrecognized characters.

### -field Reserved

### -field Count

Specifies the number of <a href="/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_micr_info">WIA_MICR_INFO</a> elements in the <b>Micr</b> sequence.

### -field Micr

Placeholder for a sequence of <b>Count</b> contiguous <a href="/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_micr_info">WIA_MICR_INFO</a> structures.

## -remarks

The header must be followed by a sequence of MICR information structures, one for each decoded MICR code, in the order the MICR codes were found and decoded.


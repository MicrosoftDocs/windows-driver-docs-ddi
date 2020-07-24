---
UID: NS:wiadef._WIA_PATCH_CODES
title: _WIA_PATCH_CODES (wiadef.h)
description: The WIA_PATCH_CODES structure stores header information for the patch code metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_patch_codes.htm
tech.root: image
ms.assetid: CFD2403B-DDD4-4318-9084-1B3E3462FBDC
ms.date: 05/03/2018
keywords: ["_WIA_PATCH_CODES structure"]
ms.keywords: WIA_PATCH_CODES, WIA_PATCH_CODES structure [Imaging Devices], _WIA_PATCH_CODES, image.wia_patch_codes, wiadef/WIA_PATCH_CODES
f1_keywords:
 - "wiadef/WIA_PATCH_CODES"
 - "WIA_PATCH_CODES"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wiadef.h
api_name:
- WIA_PATCH_CODES
targetos: Windows
req.typenames: WIA_PATCH_CODES
---

# _WIA_PATCH_CODES structure


## -description


The <b>WIA_PATCH_CODES</b> structure stores header information for the patch code metadata report of one scan job (one call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvacquireitemdata">IWiaMiniDrv::drvAcquireItemData</a>).


## -struct-fields




### -field Tag

Must be the literal 'WBAT', 4 single byte ASCII characters. 


### -field Version

Must be the value 0x00010000 (Version 1.0).


### -field Size

The complete size of this <b>WIA_PATCH_CODES</b> header structure, in bytes, including the complete size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_patch_code_info">WIA_PATCH_CODES_INFO</a> list.


### -field Count

Specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_patch_code_info">WIA_PATCH_CODES_INFO</a> elements in the PatchCodes sequence.


### -field PatchCodes

Placeholder for a sequence of <b>Count</b> contiguous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wiadef/ns-wiadef-_wia_patch_code_info">WIA_PATCH_CODES_INFO</a> structures.


## -remarks



The header must be followed by a sequence of patch code information structures, one for each detected patch code, in the order the patch codes were found and decoded.




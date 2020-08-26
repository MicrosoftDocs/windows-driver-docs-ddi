---
UID: NS:wiamindr_lh._WIAS_ENDORSER_INFO
title: _WIAS_ENDORSER_INFO (wiamindr_lh.h)
description: The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs.
old-location: image\wias_endorser_info.htm
tech.root: image
ms.assetid: 4874ddab-5443-4e03-8f49-493682dabac1
ms.date: 05/03/2018
keywords: ["WIAS_ENDORSER_INFO structure"]
ms.keywords: "*PWIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO structure pointer [Imaging Devices], WIAS_ENDORSER_INFO, WIAS_ENDORSER_INFO structure [Imaging Devices], _WIAS_ENDORSER_INFO, image.wias_endorser_info, wiamindr_lh/PWIAS_ENDORSER_INFO, wiamindr_lh/WIAS_ENDORSER_INFO, wiastrct_de79ab57-ad51-4bf0-90cb-51bd1a8352bd.xml"
f1_keywords:
 - "wiamindr_lh/WIAS_ENDORSER_INFO"
 - "WIAS_ENDORSER_INFO"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
- wiamindr_lh.h
api_name:
- WIAS_ENDORSER_INFO
targetos: Windows
req.typenames: WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO
---

# _WIAS_ENDORSER_INFO structure

## -description

The **WIAS_ENDORSER_INFO** structure holds custom endorser token/value pairs.

## -struct-fields

### -field ulPageCount

Specifies the value that will replace the $PAGE_COUNT$ token, provided that the endorser string contains that token.

### -field ulNumEndorserValues

Specifies the number of token/value pairs. This member will be 0 if there are no custom token/value pairs.

### -field pEndorserValues

Points to an array of [WIAS_ENDORSER_VALUE](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wias_endorser_value) structures, holding custom token/value pairs. If the value of the **ulNumEndorserValues** member is 0, this member should be **NULL**.

## -remarks

Currently, [wiasParseEndorserString](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasparseendorserstring) recognizes three endorser tokens: $DATE$, $TIME$, $PAGE_COUNT$, $DAY$, $MONTH$, and $YEAR$. (See *wiamdef.h*.) Any other tokens and their values must be specified in the **pEndorserValues** member of this structure.

## -see-also

[WIAS_ENDORSER_VALUE](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/ns-wiamindr_lh-_wias_endorser_value)

[wiasParseEndorserString](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamdef/nf-wiamdef-wiasparseendorserstring)

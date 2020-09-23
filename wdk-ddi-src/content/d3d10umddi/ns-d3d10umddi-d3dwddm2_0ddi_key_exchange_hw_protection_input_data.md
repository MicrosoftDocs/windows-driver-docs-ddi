---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA (d3d10umddi.h)
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA is used with D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_input_data.htm
ms.assetid: 9CF86E7B-B6EF-419C-97A9-424FFB08FF61
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure"]
ms.keywords: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_input_data
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
tech.root: display
req.typenames: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
f1_keywords:
 - D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
 - d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA structure


## -description

<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</b> is used with <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> in the implementation of Digital Rights Management (DRM).

## -struct-fields

### -field PrivateDataSize

Contains the size of the private data reserved for IHV usage. This size is determined from the <b>pPrivateInputSize</b> member returned by <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize">GetCryptoSessionPrivateDataSize</a>.

### -field HWProtectionDataSize

Contains the size of the DRM command data.

### -field pbInput

If <b>PrivateDataSize</b> is greater than 0, <b>pbInput</b>[0] – <b>pbInput</b>[<b>PrivateDataSize</b> - 1] is reserved for IHV use.



<b>pbInput</b>[<b>PrivateDataSize</b>] – <b>pbInput</b>[<b>HWProtectionDataSize</b> + <b>PrivateDataSize</b> - 1] contains the input data for the DRM command. The format and size of the DRM command is defined by the DRM specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize">GetCryptoSessionPrivateDataSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a>
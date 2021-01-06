---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA (d3d10umddi.h)
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA is used with D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_output_data.htm
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure"]
ms.keywords: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_output_data
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
req.typenames: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
f1_keywords:
 - D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
 - d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA structure


## -description

<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</b> is used with <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a> in the implementation of Digital Rights Management (DRM).

## -struct-fields

### -field PrivateDataSize

Contains the size of the private data reserved for IHV usage. This size is determined from the <b>pPrivateInputSize</b> member returned by <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize">GetCryptoSessionPrivateDataSize</a>.

### -field MaxHWProtectionDataSize

The maximum size of data that the driver can return in the output buffer. The last byte that it can write to is <b>pbOuput</b>[<b>PrivateDataSize</b> + <b>MaxHWProtectionDataSize</b> – 1].

### -field HWProtectionDataSize

Returns the size of the output data written by the driver.

### -field TransportTime

Returns the number of 100 nanosecond units spent transporting the data.

### -field ExecutionTime

Returns the number of 100 nanosecond units spent executing the content protection command.

### -field pbOutput

If <b>PrivateDataSize</b> is greater than 0, <b>pbOutput</b>[0] – <b>pbOutput</b>[<b>PrivateDataSize</b> - 1] is reserved for IHV use.



<b>pbOutput</b>[<b>PrivateDataSize</b>] – <b>pbOutput</b>[<b>MaxHWProtectionDataSize</b> + <b>PrivateDataSize</b> - 1] contains the region into which the driver should return the output data from the DRM command. The format and size of the DRM command is defined by the DRM specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_data">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_getcryptosessionprivatedatasize">GetCryptoSessionPrivateDataSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a>

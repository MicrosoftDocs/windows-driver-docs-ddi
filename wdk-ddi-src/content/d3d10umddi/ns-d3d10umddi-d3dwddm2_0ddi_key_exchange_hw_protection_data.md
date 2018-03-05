---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
title: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
author: windows-driver-content
description: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA is used with NegotiateCryptoSessionKeyExchange in the implementation of Digital Rights Management (DRM).
old-location: display\d3dwddm2_0ddi_key_exchange_hw_protection_data.htm
old-project: display
ms.assetid: BAC7B5B9-FD89-4C60-B3C2-06251110CDF5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA, D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA, display.d3dwddm2_0ddi_key_exchange_hw_protection_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA
---

# D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA structure


## -description


<b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA</b> is used with <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a> in the implementation of Digital Rights Management (DRM).


## -syntax


````
typedef struct D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA {
  UINT                                                 HWProtectionFunctionID;
  D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA  *pInputData;
  D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA *pOutputData;
  HRESULT                                              Status;
} D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA;
````


## -struct-fields




### -field HWProtectionFunctionID

Specifies the function ID of the DRM command. The values and meanings of the function ID are defined by each individual DRM component.


### -field pInputData

Pointer to a buffer containing a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_input_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</a> structure, reserved memory for IHV use, and the input data for the DRM command.


### -field pOutputData

Pointer to a buffer containing a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_output_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</a> structure, reserved memory for IHV use, and the output data for the DRM command.


### -field Status

Returns the result of the hardware DRM command.


## -remarks



A pointer to this structure is passed in as the <i>pData</i> parameter of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a> function when the <b>CryptoSession</b> object is creating using the <b>D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION</b> key exchange type.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_output_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_OUTPUT_DATA</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_key_exchange_hw_protection_input_data.md">D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_INPUT_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_KEY_EXCHANGE_HW_PROTECTION_DATA structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


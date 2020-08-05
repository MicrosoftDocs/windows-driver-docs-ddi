---
UID: NS:d3dumddi._D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
title: _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE (d3dumddi.h)
description: The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption.
old-location: display\d3dddiarg_cryptosessionkeyexchange.htm
tech.root: display
ms.assetid: 45ff38bf-7640-4b7c-ab26-ae758c9b4696
ms.date: 05/10/2018
keywords: ["D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure"]
ms.keywords: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure [Display Devices], UMDisplayDriver_param_Structs_80a0e3f6-7fa5-444f-9eeb-505a6632af8d.xml, _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, d3dumddi/D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE, display.d3dddiarg_cryptosessionkeyexchange
f1_keywords:
 - "d3dumddi/D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE"
 - "D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
targetos: Windows
req.typenames: D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE
---

# _D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure


## -description


The D3DDDIARG_CRYPTOSESSIONKEYEXCHANGE structure describes a buffer that contains the session key, which is used for encryption. 


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session that is the runtime creates when the runtime calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function. 


### -field DataSize

[in/out] The size, in bytes, of the data that the <b>pData</b> member points to. 


### -field pData

[in/out] A pointer to a buffer that contains the session key. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>
 

 


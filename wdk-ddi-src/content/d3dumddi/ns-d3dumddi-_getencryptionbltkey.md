---
UID: NS:d3dumddi._GETENCRYPTIONBLTKEY
title: _GETENCRYPTIONBLTKEY (d3dumddi.h)
description: The _GETENCRYPTIONBLTKEY structure describes an encrypted bit-block transfer (bitblt) session for which the GetEncryptionBltKey function retrieves the encryption key.
old-location: display\d3dddiarg_getencryptionbltkey.htm
tech.root: display
ms.assetid: 6f481646-b665-46cb-b551-10515b8603c5
ms.date: 05/10/2018
keywords: ["_GETENCRYPTIONBLTKEY structure"]
ms.keywords: D3DDDIARG_GETENCRYPTIONBLTKEY, D3DDDIARG_GETENCRYPTIONBLTKEY structure [Display Devices], UMDisplayDriver_param_Structs_ecaf1a03-2c4a-450e-a17a-2cc309e7c2e4.xml, _GETENCRYPTIONBLTKEY, _GETENCRYPTIONBLTKEY structure [Display Devices], d3dumddi/_GETENCRYPTIONBLTKEY, display.d3dddiarg_getencryptionbltkey
f1_keywords:
 - "d3dumddi/D3DDDIARG_GETENCRYPTIONBLTKEY"
 - "D3DDDIARG_GETENCRYPTIONBLTKEY"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_GETENCRYPTIONBLTKEY is supported beginning with the Windows 7 operating system.
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
- D3DDDIARG_GETENCRYPTIONBLTKEY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# _GETENCRYPTIONBLTKEY structure


## -description


The _GETENCRYPTIONBLTKEY structure describes an encrypted bit-block transfer (bitblt) session for which the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey">GetEncryptionBltKey</a> function retrieves the encryption key. 


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session that is created in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function. 


### -field pReadBackKey

[in] A pointer to a buffer that contains the encryption key. 


### -field KeySize

[in] The size, in bytes, of the encryption key that the <b>pReadBackKey</b> member points to. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getencryptionbltkey">GetEncryptionBltKey</a>
 

 


---
UID: NC:d3dumddi.PFND3DDDI_DECRYPTIONBLT
title: PFND3DDDI_DECRYPTIONBLT (d3dumddi.h)
description: The DecryptionBlt function writes data to a protected surface.
old-location: display\decryptionblt.htm
tech.root: display
ms.assetid: 1bfe2b9c-90f6-48bf-b0b3-30788ef94110
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DECRYPTIONBLT callback function"]
ms.keywords: DecryptionBlt, DecryptionBlt callback function [Display Devices], PFND3DDDI_DECRYPTIONBLT, PFND3DDDI_DECRYPTIONBLT callback, UserModeDisplayDriver_Functions_6c7efbab-8c07-4953-80cc-4d18080c12cc.xml, d3dumddi/DecryptionBlt, display.decryptionblt
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DecryptionBlt is supported beginning with the Windows 7 operating system.
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
req.typenames: 
f1_keywords:
 - PFND3DDDI_DECRYPTIONBLT
 - d3dumddi/PFND3DDDI_DECRYPTIONBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - DecryptionBlt
product:
 - Windows
---

# PFND3DDDI_DECRYPTIONBLT callback function


## -description

The <b>DecryptionBlt</b> function writes data to a protected surface.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a> structure that describes the parameters of the decrypted bit-block transfer (bitblt) operation.

## -returns

<b>DecryptionBlt</b> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The decrypted bitblt operation is successfully performed.|
|E_OUTOFMEMORY|DecryptionBlt could not allocate the required memory for it to complete.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the DecryptionBlt function.|

## -remarks

Hardware and drivers can optionally support <b>DecryptionBlt</b> for some crypto types. 

If the calling application requires the use of a content key, the application uses the content key to encrypt the data, and the session key to encrypt the content key before passing the content key in the block of memory that the <b>pContentKey</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a> points to. If <b>pContentKey</b> is <b>NULL</b>, it indicates that the application used the session key to encrypt the data.

If the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the <b>pIV</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a> points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvaddi_pvp_hw_iv">DXVADDI_PVP_HW_IV</a> structure and contains the initialization vector that the application used to encrypt the buffer. The driver's <b>DecryptionBlt</b> function should fail if it determines that the initialization vector was previously used for the same content key (or session key if the content key is not used). The application should increment the <b>IV</b> member of the DXVADDI_PVP_HW_IV structure for each buffer that the application encrypts. Therefore, the driver's <b>DecryptionBlt</b> function can fail if the <b>IV</b> member is less than or equal to the previous <b>IV</b> value that was passed to <b>DecryptionBlt</b>.

If the driver and hardware support partially encrypted buffers, the <b>pEncryptedBlockInfo</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a> indicates the portions of the buffer that are encrypted and the portions that are not encrypted.  If the entire buffer is encrypted, <b>pEncryptedBlockInfo</b> should be <b>NULL</b>.

<b>DecryptionBlt</b> cannot write sub-rectangles.

The Direct3D runtime verifies that the source surface specified by the <b>SrcSubResourceIndex</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a> structure is in system memory and that no stretching, color space conversion, and so on is performed. An application should ensure that the system memory buffer is properly aligned and that the buffer's size matches the destination surface. The driver should verify the memory alignment and the buffer size (<b>SrcResourceSize</b> member of D3DDDIARG_DECRYPTIONBLT) and fail if these conditions are not correct..

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_decryptionblt">D3DDDIARG_DECRYPTIONBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>


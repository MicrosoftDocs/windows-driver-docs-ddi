---
UID: NC:d3d10umddi.PFND3D11_1DDI_DECRYPTIONBLT
title: PFND3D11_1DDI_DECRYPTIONBLT (d3d10umddi.h)
description: Writes encrypted data to a protected surface.
old-location: display\decryptionblt1.htm
ms.assetid: 36aeb826-251e-404e-8ce3-6b2246ff07bc
ms.date: 05/10/2018
ms.keywords: DecryptionBlt, DecryptionBlt callback function [Display Devices], PFND3D11_1DDI_DECRYPTIONBLT, PFND3D11_1DDI_DECRYPTIONBLT callback, d3d10umddi/DecryptionBlt, display.decryptionblt1
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: 
f1_keywords:
 - "d3d10umddi/DecryptionBlt"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - DecryptionBlt
product:
 - Windows
---

# PFND3D11_1DDI_DECRYPTIONBLT callback function

## -description

Writes encrypted data to a protected surface. This function is called only if <b>D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT</b> is set in the <b>Caps</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCryptoSession

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -param hSrcResource

A handle to the resource that contains the source data.

### -param hDstResource

A pointer to the resource where the encrypted data is to be written.

### -param pEncryptedBlockInfo

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_encrypted_block_info">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted. 

<div class="alert"><b>Note</b>  If the entire buffer is encrypted, <i>pEncryptedBlockinfo</i> should be set to NULL.</div>
<div> </div>

### -param ContentKeySize

The size, in bytes, of the content key.

### -param pContentKey

A pointer to a block of memory that contains the content key that is required to decrypt the bit-block transfer (bitblt) data.

If <i>pContentKey</i> is not set to NULL, the buffer data is encrypted by using the specified content key. The data for this key is encrypted by using the session key with the AES-ECB algorithm.

If <i>pContentKey</i> is NULL, the graphics adapter does not require a separate content key to decrypt the data. In this case, the session key is used to decrypt the data.

### -param IVSize

The size, in bytes, of the initialization vector (IV).

### -param pIV

A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  <p class="note">If <i>pIV</i> is NULL, the graphics adapter does not require a separate initialization vector to decrypt the data. That is, the session key is used to decrypt the data. 


</div>
<div> </div>

## -returns

This callback function does not return a value.

## -remarks

For 128-bit AES-CTR encryption, the <i>pIV</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a> structure that is allocated by the application. However, the actual contents of this structure are filled in by the driver or graphics adapter.  When the first IV is generated, the driver or adapter  initializes the <b>IV</b> member of this structure to a random number. For each subsequent IV, the caller increments the <b>IV</b> member, ensuring that the value always increases. This procedure enables the application to validate that the same IV is never used more than once with the same key pair.



For other encryption types, a different structure might be used, or the encryption might not use an IV.



<div class="alert"><b>Note</b>  This function does not honor a Direct3D version 11 predicate that may have been set.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_encrypted_block_info">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_content_protection_caps">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>


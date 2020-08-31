---
UID: NC:d3d10umddi.PFND3D11_1DDI_ENCRYPTIONBLT
title: PFND3D11_1DDI_ENCRYPTIONBLT (d3d10umddi.h)
description: Reads encrypted data from a protected surface.
old-location: display\encryptionblt1.htm
ms.assetid: ea6f1b8c-d65a-4d6d-a7ae-998374bf5bfb
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_ENCRYPTIONBLT callback function"]
ms.keywords: EncryptionBlt, EncryptionBlt callback function [Display Devices], PFND3D11_1DDI_ENCRYPTIONBLT, PFND3D11_1DDI_ENCRYPTIONBLT callback, d3d10umddi/EncryptionBlt, display.encryptionblt1, display.pfnencryptionblt1
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
 - PFND3D11_1DDI_ENCRYPTIONBLT
 - d3d10umddi/PFND3D11_1DDI_ENCRYPTIONBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - EncryptionBlt
product:
 - Windows
---

# PFND3D11_1DDI_ENCRYPTIONBLT callback function


## -description

Reads encrypted data from a protected surface.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCryptoSession

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -param hSrcResource

A handle to the resource that contains the source data.

### -param hDstResource

A pointer to the resource where the encrypted data is to be written.

### -param IVSize

The size, in bytes, of the initialization vector (IV).

### -param pIV

A pointer to a block of memory that contains the initialization vector that is required to encrypt the bitblt data. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  <p class="note">If <i>pIV</i> is NULL, the graphics adapter does not require a separate initialization vector to encrypt the data. That is, the session key is used to encrypt the data. 


</div>
<div> </div>

## -remarks

This function has the following limitations:



<ul>
<li>
The function cannot read back subrectangles or partially encrypted surfaces. 


</li>
<li>
The function cannot read back partially encrypted buffers. Many hardware-based encryption solutions will not allow nonencrypted reads from protected memory.

</li>
<li>
The protected surface must be either an off-screen plain surface or a render target. 


</li>
<li>
The destination surface must be a system-memory surface that was created by using the proper alignment, as described earlier. 


</li>
<li>
The protected surface cannot be multisampled. 


</li>
<li>
The function does not support stretching or color space conversion. 


</li>
</ul>
For 128-bit AES-CTR encryption, the <i>pIV</i> parameter points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a> structure that is allocated by the application. However, the actual contents of this structure are filled in by the driver or graphics adapter.  When the first IV is generated, the driver or adapter  initializes the <b>IV</b> member of this structure to a random number. For each subsequent IV, the caller increments the <b>IV</b> member, ensuring that the value always increases. This procedure enables the application to validate that the same IV is never used more than once with the same key pair.



For other encryption types, a different structure might be used, or the encryption might not use an IV.



<div class="alert"><b>Note</b>  This function does not honor a Direct3D version 11 predicate that may have been set.</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_aes_ctr_iv">D3D11_1DDI_AES_CTR_IV</a>


---
UID: NC:d3d10umddi.PFND3D11_1DDI_DECRYPTIONBLT
title: PFND3D11_1DDI_DECRYPTIONBLT
author: windows-driver-content
description: Writes encrypted data to a protected surface.
old-location: display\decryptionblt1.htm
old-project: display
ms.assetid: 36aeb826-251e-404e-8ce3-6b2246ff07bc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DecryptionBlt, DecryptionBlt callback function [Display Devices], PFND3D11_1DDI_DECRYPTIONBLT, d3d10umddi/DecryptionBlt, display.decryptionblt1
ms.prod: windows-hardware
ms.technology: windows-devices
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	DecryptionBlt
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11_1DDI_DECRYPTIONBLT callback


## -description


Writes encrypted data to a protected surface. This function is called only if <b>D3D11_1DDI_CONTENT_PROTECTION_CAPS_DECRYPTION_BLT</b> is set in the <b>Caps</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450936">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a> structure.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the driver's private data for the cryptographic session. This handle was created by the Direct3D runtime and passed to the driver in the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.


### -param hSrcResource [in]

A handle to the resource that contains the source data.


### -param hDstResource [in]

A pointer to the resource where the encrypted data is to be written.




### -param *pEncryptedBlockInfo [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406446">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted. 

<div class="alert"><b>Note</b>  If the entire buffer is encrypted, <i>pEncryptedBlockinfo</i> should be set to NULL.</div>
<div> </div>

### -param ContentKeySize [in]

The size, in bytes, of the content key.


### -param *pContentKey [in]

A pointer to a block of memory that contains the content key that is required to decrypt the bit-block transfer (bitblt) data.

If <i>pContentKey</i> is not set to NULL, the buffer data is encrypted by using the specified content key. The data for this key is encrypted by using the session key with the AES-ECB algorithm.

If <i>pContentKey</i> is NULL, the graphics adapter does not require a separate content key to decrypt the data. In this case, the session key is used to decrypt the data.


### -param IVSize [in]

The size, in bytes, of the initialization vector (IV).


### -param *pIV [in]

A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. For more information, see the Remarks section.

<div class="alert"><b>Note</b>  <p class="note">If <i>pIV</i> is NULL, the graphics adapter does not require a separate initialization vector to decrypt the data. That is, the session key is used to decrypt the data. 


</div>
<div> </div>

## -returns



This callback function does not return a value.




## -remarks



For 128-bit AES-CTR encryption, the <i>pIV</i> parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406334">D3D11_1DDI_AES_CTR_IV</a> structure that is allocated by the application. However, the actual contents of this structure are filled in by the driver or graphics adapter.  When the first IV is generated, the driver or adapter  initializes the <b>IV</b> member of this structure to a random number. For each subsequent IV, the caller increments the <b>IV</b> member, ensuring that the value always increases. This procedure enables the application to validate that the same IV is never used more than once with the same key pair.



For other encryption types, a different structure might be used, or the encryption might not use an IV.



<div class="alert"><b>Note</b>  This function does not honor a Direct3D version 11 predicate that may have been set.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406334">D3D11_1DDI_AES_CTR_IV</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406446">D3D11_1DDI_ENCRYPTED_BLOCK_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450936">D3D11_1DDI_VIDEO_CONTENT_PROTECTION_CAPS</a>
 

 


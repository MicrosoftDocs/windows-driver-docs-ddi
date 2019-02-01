---
UID: NS:d3dumddi._D3DDDIARG_DECRYPTIONBLT
title: _D3DDDIARG_DECRYPTIONBLT (d3dumddi.h)
description: The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the DecryptionBlt function.
old-location: display\d3dddiarg_decryptionblt.htm
tech.root: display
ms.assetid: cc11e153-6be6-4fbc-9535-98bab7ed2b90
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_DECRYPTIONBLT, D3DDDIARG_DECRYPTIONBLT structure [Display Devices], UMDisplayDriver_param_Structs_1d0c0adb-cfde-47fd-b17c-1acc15de25cd.xml, _D3DDDIARG_DECRYPTIONBLT, d3dumddi/D3DDDIARG_DECRYPTIONBLT, display.d3dddiarg_decryptionblt
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_DECRYPTIONBLT is supported beginning with the Windows 7 operating system.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDIARG_DECRYPTIONBLT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DECRYPTIONBLT
---

# _D3DDDIARG_DECRYPTIONBLT structure


## -description


The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the <a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a> function. 


## -struct-fields




### -field hCryptoSession

[in] A handle to the encryption session. 


### -field hSrcResource

[in] A handle to the source resource.


### -field SrcSubResourceIndex

[in] The index to the source surface within the resource. 


### -field hDstResource

[in] A handle to the destination resource. 


### -field DstSubResourceIndex

[in] The index to the destination surface within the resource. 


### -field SrcResourceSize

[in] The size, in bytes, of the source resource. 


### -field pEncryptedBlockInfo

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544298">D3DDDIENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted. 


### -field pContentKey

[in] A pointer to a block of memory that contains the content key that is required to decrypt the bitblt data. If <b>pContentKey</b> is <b>NULL</b>, hardware does not require a separate content key to decrypt the data. That is, the session key is used to encrypt the data. 


### -field pIV

[in] A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. If <b>pIV</b> is <b>NULL</b>, hardware does not require a separate initialization vector to decrypt the data. That is, the session key is used to encrypt the data. 


## -remarks



A pointer to a populated D3DDDIARG_DECRYPTIONBLT structure is passed to the driver's <a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a> function to write data to a protected surface. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544298">D3DDDIENCRYPTED_BLOCK_INFO</a>



<a href="https://msdn.microsoft.com/1bfe2b9c-90f6-48bf-b0b3-30788ef94110">DecryptionBlt</a>
 

 


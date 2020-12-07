---
UID: NS:d3dumddi._D3DDDIARG_DECRYPTIONBLT
title: _D3DDDIARG_DECRYPTIONBLT (d3dumddi.h)
description: The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the DecryptionBlt function.
old-location: display\d3dddiarg_decryptionblt.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_DECRYPTIONBLT structure"]
ms.keywords: D3DDDIARG_DECRYPTIONBLT, D3DDDIARG_DECRYPTIONBLT structure [Display Devices], UMDisplayDriver_param_Structs_1d0c0adb-cfde-47fd-b17c-1acc15de25cd.xml, _D3DDDIARG_DECRYPTIONBLT, d3dumddi/D3DDDIARG_DECRYPTIONBLT, display.d3dddiarg_decryptionblt
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
targetos: Windows
req.typenames: D3DDDIARG_DECRYPTIONBLT
f1_keywords:
 - _D3DDDIARG_DECRYPTIONBLT
 - d3dumddi/_D3DDDIARG_DECRYPTIONBLT
 - D3DDDIARG_DECRYPTIONBLT
 - d3dumddi/D3DDDIARG_DECRYPTIONBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - D3DDDIARG_DECRYPTIONBLT
---

# _D3DDDIARG_DECRYPTIONBLT structure


## -description

The D3DDDIARG_DECRYPTIONBLT structure describes the parameters of an decrypted bit-block transfer (bitblt) in a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt">DecryptionBlt</a> function.

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

[in] A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiencrypted_block_info">D3DDDIENCRYPTED_BLOCK_INFO</a> structure that describes the portions of the buffer that are encrypted.

### -field pContentKey

[in] A pointer to a block of memory that contains the content key that is required to decrypt the bitblt data. If <b>pContentKey</b> is <b>NULL</b>, hardware does not require a separate content key to decrypt the data. That is, the session key is used to encrypt the data.

### -field pIV

[in] A pointer to a block of memory that contains the initialization vector that is required to decrypt the bitblt data. If <b>pIV</b> is <b>NULL</b>, hardware does not require a separate initialization vector to decrypt the data. That is, the session key is used to encrypt the data.

## -remarks

A pointer to a populated D3DDDIARG_DECRYPTIONBLT structure is passed to the driver's <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt">DecryptionBlt</a> function to write data to a protected surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiencrypted_block_info">D3DDDIENCRYPTED_BLOCK_INFO</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_decryptionblt">DecryptionBlt</a>

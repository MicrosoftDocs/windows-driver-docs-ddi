---
UID: NS:d3dumddi._D3DDDIARG_ENCRYPTIONBLT
title: _D3DDDIARG_ENCRYPTIONBLT (d3dumddi.h)
description: The D3DDDIARG_ENCRYPTIONBLT structure describes the parameters of an encrypted bit-block transfer (bitblt) in a call to the EncryptionBlt function.
old-location: display\d3dddiarg_encryptionblt.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDIARG_ENCRYPTIONBLT structure"]
ms.keywords: D3DDDIARG_ENCRYPTIONBLT, D3DDDIARG_ENCRYPTIONBLT structure [Display Devices], UMDisplayDriver_param_Structs_b76b39b2-87b0-453d-b6c5-e59b38249684.xml, _D3DDDIARG_ENCRYPTIONBLT, d3dumddi/D3DDDIARG_ENCRYPTIONBLT, display.d3dddiarg_encryptionblt
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_ENCRYPTIONBLT is supported beginning with the Windows 7 operating system.
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
req.typenames: D3DDDIARG_ENCRYPTIONBLT
f1_keywords:
 - _D3DDDIARG_ENCRYPTIONBLT
 - d3dumddi/_D3DDDIARG_ENCRYPTIONBLT
 - D3DDDIARG_ENCRYPTIONBLT
 - d3dumddi/D3DDDIARG_ENCRYPTIONBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dumddi.h
api_name:
 - _D3DDDIARG_ENCRYPTIONBLT
 - D3DDDIARG_ENCRYPTIONBLT
---

# _D3DDDIARG_ENCRYPTIONBLT structure


## -description

The D3DDDIARG_ENCRYPTIONBLT structure describes the parameters of an encrypted bit-block transfer (bitblt) in a call to the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a> function.

## -struct-fields

### -field hCryptoSession [in]

A handle to the encryption session.

### -field hSrcResource [in]

A handle to the source resource.

### -field SrcSubResourceIndex [in]

The index to the source surface within the resource.

### -field hDstResource [in]

A handle to the destination resource.

### -field DstSubResourceIndex [in]

The index to the destination surface within the resource.

### -field DstResourceSize [in]

The size, in bytes, of the destination resource.

### -field pIV [out]

A pointer to a block of memory in which <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a> returns the initialization vector that is required to decrypt the bitblt data. If <b>pIV</b> is <b>NULL</b>, hardware does not require a separate key to decrypt the data that is read back.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a>


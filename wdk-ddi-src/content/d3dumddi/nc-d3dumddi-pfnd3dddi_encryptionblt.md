---
UID: NC:d3dumddi.PFND3DDDI_ENCRYPTIONBLT
title: PFND3DDDI_ENCRYPTIONBLT (d3dumddi.h)
description: The EncryptionBlt function reads encrypted data from a protected surface.
old-location: display\encryptionblt.htm
tech.root: display
ms.assetid: a92bfff7-8af6-48c3-9e7f-95b9426aaaf2
ms.date: 05/10/2018
keywords: ["PFND3DDDI_ENCRYPTIONBLT callback function"]
ms.keywords: EncryptionBlt, EncryptionBlt callback function [Display Devices], PFND3DDDI_ENCRYPTIONBLT, PFND3DDDI_ENCRYPTIONBLT callback, UserModeDisplayDriver_Functions_49cc68db-1210-44e5-80f1-347210dc6cf3.xml, d3dumddi/EncryptionBlt, display.encryptionblt
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: EncryptionBlt is supported beginning with the Windows 7 operating system.
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
 - PFND3DDDI_ENCRYPTIONBLT
 - d3dumddi/PFND3DDDI_ENCRYPTIONBLT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - EncryptionBlt
product:
 - Windows
---

# PFND3DDDI_ENCRYPTIONBLT callback function


## -description

The <i>EncryptionBlt</i> function reads encrypted data from a protected surface.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a> structure that describes the parameters of the encrypted bit-block transfer (bitblt) operation.

## -returns

<i>EncryptionBlt</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The encrypted bitblt operation is successfully performed.|
|E_OUTOFMEMORY|EncryptionBlt could not allocate the required memory for it to complete.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the EncryptionBlt function.|

## -remarks

Hardware and drivers can optionally support <i>EncryptionBlt</i>. Some hardware might also require to use a separate key to decrypt the data that is read back. The driver returns this key in a block of memory that the <b>pIV</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a> points to. 

If the driver and hardware use a separate key for the encryption bitblt, the application must recognize this fact and use the key. 

If the crypto type is D3DCRYPTOTYPE_AES128_CTR, <b>pIV</b> points to a D3DAES_CTR_IV structure that the application allocates. However, the actual contents of the D3DAES_CTR_IV structure are filled in by the driver and hardware. When the driver and hardware generate the first initialization vector, they should initialize the <b>IV</b> member of the D3DAES_CTR_IV structure to a random number (that is not too big). Each subsequent initialization vector should simply increment the <b>IV</b> member, which ensures that the <b>IV</b> always increases in value. This fact enables the application to validate that the same <b>IV</b> is never used multiple times with the same key pair.

<i>EncryptionBlt</i> cannot read back sub-rectangles. <i>EncryptionBlt</i> also cannot read back partially encrypted buffers because many of the hardware-based solutions do not allow non-encrypted reads from protected memory.

The Direct3D runtime verifies that the destination surface specified by the <b>DstSubResourceIndex</b> member of D3DDDIARG_ENCRYPTIONBLT is in system memory and that no stretching, color space conversion, and so on is performed. An application should ensure that the system memory buffer is properly aligned and that the buffer's size matches the source surface. The driver should verify the memory alignment and the buffer size (<b>DstResourceSize</b> member of D3DDDIARG_ENCRYPTIONBLT) and fail if these conditions are not correct.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_encryptionblt">D3DDDIARG_ENCRYPTIONBLT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>


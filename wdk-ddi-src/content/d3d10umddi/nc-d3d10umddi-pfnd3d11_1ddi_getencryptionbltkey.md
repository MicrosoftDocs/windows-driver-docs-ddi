---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETENCRYPTIONBLTKEY
title: PFND3D11_1DDI_GETENCRYPTIONBLTKEY (d3d10umddi.h)
description: Queries the key that is used to decrypt the data returned by the EncryptionBlt(D3D11_1) function.
old-location: display\getencryptionbltkey1.htm
ms.assetid: f1d3a443-7980-4894-b6a9-04c0886c6996
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback function"]
ms.keywords: PFND3D11_1DDI_GETENCRYPTIONBLTKEY, PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback, d3d10umddi/pfnGetEncryptionBltKey, display.getencryptionbltkey1, pfnGetEncryptionBltKey, pfnGetEncryptionBltKey callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,Available in Windows Desktop version 10.0.10030.0
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
 - PFND3D11_1DDI_GETENCRYPTIONBLTKEY
 - d3d10umddi/PFND3D11_1DDI_GETENCRYPTIONBLTKEY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnGetEncryptionBltKey
product:
 - Windows
---

# PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback function


## -description

Queries the key that is used to decrypt the data returned by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt">EncryptionBlt(D3D11_1)</a> function.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param hCryptoSession

A handle to the cryptographic session that was created in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function.

### -param KeySize

The size, in bytes, of the encryption key that the <i>pReadBackKey</i> parameter points to.

### -param pReadbackKey

A pointer to a buffer that contains the encryption key.

## -remarks

When the <b>GetEncryptionBltKey</b> function is called, the display miniport driver should generate a new encryption key.  If the cryptographic session is using  the <b>D3DCRYPTOTYPE_AES128_CTR</b> cryptographic type, the driver or graphics adapter should encrypt the data that is referenced by the   <i>pReadbackKey</i> parameter by using the session key with the AES-ECB algorithm.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_encryptionblt">EncryptionBlt(D3D11_1)</a>


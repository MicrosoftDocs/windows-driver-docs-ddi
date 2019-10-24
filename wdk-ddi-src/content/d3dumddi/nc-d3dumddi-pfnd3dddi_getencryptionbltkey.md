---
UID: NC:d3dumddi.PFND3DDDI_GETENCRYPTIONBLTKEY
title: PFND3DDDI_GETENCRYPTIONBLTKEY (d3dumddi.h)
description: The GetEncryptionBltKey function returns the key that is used to decrypt the data that the driver's EncryptionBlt function returns.
old-location: display\getencryptionbltkey.htm
tech.root: display
ms.assetid: b3c3e792-bc8a-485e-a208-66b7d921cc15
ms.date: 05/10/2018
ms.keywords: GetEncryptionBltKey, GetEncryptionBltKey callback function [Display Devices], PFND3DDDI_GETENCRYPTIONBLTKEY, PFND3DDDI_GETENCRYPTIONBLTKEY callback, UserModeDisplayDriver_Functions_c20ad527-141e-404f-a52e-47b893b2a2bb.xml, d3dumddi/GetEncryptionBltKey, display.getencryptionbltkey
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetEncryptionBltKey is supported beginning with the Windows 7 operating system.
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
 - "d3dumddi/GetEncryptionBltKey"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - GetEncryptionBltKey
product:
 - Windows
---

# PFND3DDDI_GETENCRYPTIONBLTKEY callback function

## -description

The <i>GetEncryptionBltKey</i> function returns the key that is used to decrypt the data that the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a> function returns.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_getencryptionbltkey">D3DDDIARG_GETENCRYPTIONBLTKEY</a> structure that describes the key for an encrypted session.

## -returns

<i>GetEncryptionBltKey</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The key for an encrypted session is successfully retrieved.|
|D3DDDIERR_NOTAVAILABLE|The driver does not support the GetEncryptionBltKey function.|

## -remarks

The hardware and driver can optionally support the <i>GetEncryptionBltKey</i> function for all crypto types.  

Each time the Direct3D runtime calls the driver's <i>GetEncryptionBltKey</i> function, the driver should generate a new read-back key. If the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the driver and hardware should encrypt the read-back key with the session key.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession">CreateCryptoSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_getencryptionbltkey">D3DDDIARG_GETENCRYPTIONBLTKEY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_encryptionblt">EncryptionBlt</a>


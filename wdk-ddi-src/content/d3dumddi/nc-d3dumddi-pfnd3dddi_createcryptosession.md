---
UID: NC:d3dumddi.PFND3DDDI_CREATECRYPTOSESSION
title: PFND3DDDI_CREATECRYPTOSESSION (d3dumddi.h)
description: The CreateCryptoSession function creates a crypto session that the Direct3D runtime uses to manage a session key and to perform crypto operations into and out of protected memory.
old-location: display\createcryptosession.htm
tech.root: display
ms.assetid: 85d4ae6c-059d-4256-bdda-18de3d20537a
ms.date: 05/10/2018
keywords: ["PFND3DDDI_CREATECRYPTOSESSION callback function"]
ms.keywords: CreateCryptoSession, CreateCryptoSession callback function [Display Devices], PFND3DDDI_CREATECRYPTOSESSION, PFND3DDDI_CREATECRYPTOSESSION callback, UserModeDisplayDriver_Functions_057e3836-924b-4f64-84fb-53464e71d716.xml, d3dumddi/CreateCryptoSession, display.createcryptosession
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 7.
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
 - "d3dumddi/CreateCryptoSession"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - CreateCryptoSession
product:
 - Windows
---

# PFND3DDDI_CREATECRYPTOSESSION callback function

## -description

The <b>CreateCryptoSession</b> function creates a crypto session that the Direct3D runtime uses to manage a session key and to perform crypto operations into and out of protected memory.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param Arg2

pData [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.

## -returns

<b>CreateCryptoSession</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The crypto session is successfully created. | 
| **E_OUTOFMEMORY** | [CreateCryptoSession](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession)  could not allocate the required memory for it to complete. | 
| **D3DDDIERR_NOTAVAILABLE** | The driver does not support the GUID that is specified in the CryptoTypemember of the [D3DDDIARG_CREATECRYPTOSESSION](https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession) structure or the NULL_GUID (all zeros) is specified in the CryptoTypemember. | 
| **D3DDDIERR_UNSUPPORTEDCRYPTO** | The driver does not support the crypto type for the specified decode type. |

## -remarks

If the <b>DecodeProfile</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure is NULL_GUID, the crypto session will not be used for DirectX Video Acceleration (DirectX VA) decoding. If <b>DecodeProfile</b> is not <b>NULL</b> GUID, the driver should fail with D3DDDIERR_UNSUPPORTEDCRYPTO if the crypto type in the <b>CryptoType</b> member is not supported by the decode profile. 

The driver returns a handle for the crypto session in the <b>hCryptoSession</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> that the runtime passes in all subsequent crypto session calls (for example, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange">CryptoSessionKeyExchange</a>). 

The driver must keep track of the display device (<b>hDevice</b>) that was used to create the crypto session. The driver should fail all subsequent calls that use this created crypto session if the display device that is specified in those calls is different from the display device that was used to create the crypto session.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange">CryptoSessionKeyExchange</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a>


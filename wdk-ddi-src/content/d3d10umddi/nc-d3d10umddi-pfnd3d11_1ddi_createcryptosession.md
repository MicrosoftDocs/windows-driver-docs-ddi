---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATECRYPTOSESSION
title: PFND3D11_1DDI_CREATECRYPTOSESSION (d3d10umddi.h)
description: Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.
old-location: display\createcryptosession1.htm
ms.assetid: 3c31efc3-b844-4e51-947d-b48f36020766
ms.date: 05/10/2018
ms.keywords: CreateCryptoSession, CreateCryptoSession callback function [Display Devices], PFND3D11_1DDI_CREATECRYPTOSESSION, PFND3D11_1DDI_CREATECRYPTOSESSION callback, d3d10umddi/CreateCryptoSession, display.createcryptosession1
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
 - "d3d10umddi/CreateCryptoSession"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - CreateCryptoSession
product:
 - Windows
---

# PFND3D11_1DDI_CREATECRYPTOSESSION callback function

## -description

Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.

## -parameters

### -param hDevice

A handle to the display device (graphics context).

### -param pCreateData

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure. This structure specifies the attributes of the cryptographic session to be created.

### -param hCryptoSession

A handle to the driver's private data for the cryptographic session. For more information, see the Remarks section.

### -param hRTCryptoSession

A handle to the cryptographic session that the driver should use when it calls back into the Direct3D runtime.

## -returns

Returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The authenticated channel was created successfully. | 
| **D3DDDIERR_DEVICEREMOVED** | The graphics adapter was removed. | 
| **D3DDDIERR_UNSUPPORTEDCRYPTO** | A cryptographic type was specified that is not supported by the decode profile. | 
| **E_OUTOFMEMORY** | Memory was not available to complete the operation. |

## -remarks

The Direct3D runtime calls <i>CreateCryptoSession</i> to create a cryptographic session that the runtime uses to manage a session key and to perform cryptographic operations for video content that is stored in protected memory. 


The  runtime calls <i>CreateCryptoSession</i> after it has called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize">CalcPrivateCryptoSessionSize</a> to determine the size in bytes for the private data that the driver requires for the cryptographic session. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the cryptographic session.

When the runtime  calls <i>CreateCryptoSession</i>, it passes the handle to the private data memory in the <i>hCryptoSession</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a>, if the display device that is specified in those calls is different from the display device that was used to create the cryptographic session. 



If the <b>DecodeProfile</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure is set to <b>NULL_GUID</b>, the cryptographic session will not be used for DirectX Video Acceleration (DXVA) decoding. If <b>DecodeProfile</b> is not set to <b>NULL_GUID</b>, the driver should fail the call with <b>D3DDDIERR_UNSUPPORTEDCRYPTO</b> if the <b>CryptoType</b> member is set to a cryptographic type that is not supported by the decode profile.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_calcprivatecryptosessionsize">CalcPrivateCryptoSessionSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11_1ddiarg_createcryptosession">D3D11_1DDIARG_CREATECRYPTOSESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange">NegotiateCryptoSessionKeyExchange</a>


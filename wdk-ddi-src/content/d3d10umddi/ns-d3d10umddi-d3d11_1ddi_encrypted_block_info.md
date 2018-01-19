---
UID: NS:d3d10umddi.D3D11_1DDI_ENCRYPTED_BLOCK_INFO
title: D3D11_1DDI_ENCRYPTED_BLOCK_INFO
author: windows-driver-content
description: Specifies which bytes in a video surface are encrypted.
old-location: display\d3d11_1ddi_encrypted_block_info.htm
old-project: display
ms.assetid: 36d7fab0-e343-4236-9d13-93cc0e41721e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_ENCRYPTED_BLOCK_INFO, D3D11_1DDI_ENCRYPTED_BLOCK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_ENCRYPTED_BLOCK_INFO
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_ENCRYPTED_BLOCK_INFO
---

# D3D11_1DDI_ENCRYPTED_BLOCK_INFO structure



## -description
Specifies which bytes in a video surface are encrypted.



## -syntax

````
typedef struct D3D11_1DDI_ENCRYPTED_BLOCK_INFO {
  UINT NumEncryptedBytesAtBeginning;
  UINT NumBytesInSkipPattern;
  UINT NumBytesInEncryptPattern;
} D3D11_1DDI_ENCRYPTED_BLOCK_INFO;
````


## -struct-fields

### -field NumEncryptedBytesAtBeginning

The number of bytes that are encrypted at the start of the buffer.


### -field NumBytesInSkipPattern

The number of bytes that are skipped after the first <b>NumEncryptedBytesAtBeginning</b> bytes, and then after each block of <b>NumBytesInEncryptPattern</b> bytes. Skipped bytes are not encrypted.


### -field NumBytesInEncryptPattern

The number of bytes that are encrypted after each block of skipped bytes.

The skip and encrypt pattern is then repeated until the buffer ends. For more information about the skip-encrypt pattern, see the Remarks section.


## -remarks
Because the buffer's encrypted portion is specified in bytes, an application must ensure that the encrypted blocks match the GPU's crypto-block alignment.

The following examples show how the runtime can partition a buffer's encryption.</p>
---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
title: D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
author: windows-driver-content
description: Creates a crypto session policy.
old-location: display\d3d12ddiarg-create-crypto-session-policy-0030.htm
old-project: display
ms.assetid: b7574112-2cac-4bec-9039-9afeef4d2f51
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030, D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
req.alt-loc: d3d12umddi.h
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
req.typenames: D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
---

# D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030 structure



## -description
Creates a crypto session policy.



## -syntax

````
typedef struct _D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030 {
  const void *  pKeyInfo;
  UINT          KeyInfoSize;
} D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030, D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030;
````


## -struct-fields

### -field pKeyInfo

The key info.


### -field KeyInfoSize

The key info size.


## -remarks

---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
title: D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
author: windows-driver-content
description: Creates a crypto session policy.
old-location: display\d3d12ddiarg-create-crypto-session-policy-0030.htm
old-project: display
ms.assetid: b7574112-2cac-4bec-9039-9afeef4d2f51
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030, D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030 structure [Display Devices], E, G, I, L, N, O, P, R, S, T, Y, _, d3d12umddi/D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030, display.d3d12ddiarg-create-crypto-session-policy-0030"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d12umddi.h
apiname:
-	D3D12DDIARG_CREATE_CRYPTO_SESSION_POLICY_0030
product: Windows
targetos: Windows
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


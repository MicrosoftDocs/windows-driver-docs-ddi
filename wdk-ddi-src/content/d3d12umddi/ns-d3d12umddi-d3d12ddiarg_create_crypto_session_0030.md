---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_CRYPTO_SESSION_0030
title: D3D12DDIARG_CREATE_CRYPTO_SESSION_0030
author: windows-driver-content
description: Creates a crypto session.
old-location: display\d3d12ddiarg-create-crypto-session-0030.htm
old-project: display
ms.assetid: 71d65f25-ef9c-4a3d-ad1d-1d55e73bc0cb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 structure [Display Devices], display.d3d12ddiarg-create-crypto-session-0030, d3d12umddi/D3D12DDIARG_CREATE_CRYPTO_SESSION_0030, D3D12DDIARG_CREATE_CRYPTO_SESSION_0030
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
-	D3D12DDIARG_CREATE_CRYPTO_SESSION_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_CRYPTO_SESSION_0030
---

# D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 structure


## -description


Creates a crypto session.


## -syntax


````
typedef struct _D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 {
  UINT                                     NodeMask;
  GUID                                     DecodeProfile;
  GUID                                     ContentProtectionSystem;
  D3D12DDI_BITSTREAM_ENCRYPTION_TYPE_0030  BitstreamEncryption;
  D3D12DDI_CRYPTO_SESSION_FLAGS_0030       Flags;
} D3D12DDIARG_CREATE_CRYPTO_SESSION_0030, D3D12DDIARG_CREATE_CRYPTO_SESSION_0030;
````


## -struct-fields




### -field NodeMask

Represents the set of nodes.


### -field DecodeProfile

The decode profile.


### -field ContentProtectionSystem

The content protection system.


### -field BitstreamEncryption

The bitstream encryption.


### -field Flags

The crypto session flags.


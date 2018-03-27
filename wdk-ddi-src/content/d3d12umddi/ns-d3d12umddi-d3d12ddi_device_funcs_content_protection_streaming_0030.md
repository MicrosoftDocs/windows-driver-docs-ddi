---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
title: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
author: windows-driver-content
description: Device function for content protection streaming.
old-location: display\d3d12ddi-device-funcs-content-protection-streaming-0030.htm
old-project: display
ms.assetid: 5ddf67c1-5ee7-4948-b631-45aeb031a293
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030, D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030, display.d3d12ddi-device-funcs-content-protection-streaming-0030
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
---

# D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 structure


## -description


Device function for content protection streaming.


## -struct-fields




### -field pfnCalcPrivateCryptoSessionSize

Calculate private crypto session size.


### -field pfnCreateCryptoSession

Create crypto session.


### -field pfnCalcPrivateOpenedCryptoSessionSize

Calculate private opened crypto session size.


### -field pfnOpenCryptoSession

Open crypto session.


### -field pfnDestroyCryptoSession

Destroy crypto session.


### -field pfnGetKeyBaseData

Get key base data.


### -field pfnCalcPrivateCryptoSessionPolicySize

Calculate private crypto session policy size.


### -field pfnCreateCryptoSessionPolicy

Create crypto session policy.


### -field pfnCalcPrivateOpenedCryptoSessionPolicySize

Calculate private opened crypto session policy size.


### -field pfnOpenCryptoSessionPolicy

Open crypto session policy.


### -field pfnDestroyCryptoSessionPolicy

Destroy crypto session policy.


### -field pfnTransformEncryptedData

Transform encrypted data.


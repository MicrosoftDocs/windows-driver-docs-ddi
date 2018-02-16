---
UID: NS:d3d10umddi.D3D11_1DDI_AES_CTR_IV
title: D3D11_1DDI_AES_CTR_IV
author: windows-driver-content
description: Contains an initialization vector (IV) for 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption.
old-location: display\d3d11_1ddi_aes_ctr_iv.htm
old-project: display
ms.assetid: 56228a1d-ca3b-4bd4-850c-af736e91494c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d11_1ddi_aes_ctr_iv, D3D11_1DDI_AES_CTR_IV, D3D11_1DDI_AES_CTR_IV structure [Display Devices], d3d10umddi/D3D11_1DDI_AES_CTR_IV
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
-	d3d10umddi.h
apiname:
-	D3D11_1DDI_AES_CTR_IV
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_AES_CTR_IV
---

# D3D11_1DDI_AES_CTR_IV structure


## -description


Contains an initialization vector (IV) for 128-bit Advanced Encryption Standard CTR mode (AES-CTR) block cipher encryption.


## -syntax


````
typedef struct D3D11_1DDI_AES_CTR_IV {
  UINT64 IV;
  UINT64 Count;
} D3D11_1DDI_AES_CTR_IV;
````


## -struct-fields




### -field IV

The IV, in big-endian format.


### -field Count

The block count, in big-endian format.


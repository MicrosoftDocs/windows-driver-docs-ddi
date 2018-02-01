---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
title: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
author: windows-driver-content
description: Device function for content protection streaming.
old-location: display\d3d12ddi-device-funcs-content-protection-streaming-0030.htm
old-project: display
ms.assetid: 5ddf67c1-5ee7-4948-b631-45aeb031a293
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi-device-funcs-content-protection-streaming-0030, D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 structure [Display Devices], D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030, d3d12umddi/D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
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
-	D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030
---

# D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 structure


## -description


Device function for content protection streaming.


## -syntax


````
typedef struct _D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030 {
  PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030              pfnCalcPrivateCryptoSessionSize;
  PFND3D12DDI_CREATECRYPTOSESSION_0030                       pfnCreateCryptoSession;
  PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONSIZE_0030        pfnCalcPrivateOpenedCryptoSessionSize;
  PFND3D12DDI_OPENCRYPTOSESSION_0030                         pfnOpenCryptoSession;
  PFND3D12DDI_DESTROYCRYPTOSESSION_0030                      pfnDestroyCryptoSession;
  PFND3D12DDI_GETKEYBASEDATA_0030                            pfnGetKeyBaseData;
  PFND3D12DDI_CALCPRIVATECRYPTOSESSIONPOLICYSIZE_0030        pfnCalcPrivateCryptoSessionPolicySize;
  PFND3D12DDI_CREATECRYPTOSESSIONPOLICY_0030                 pfnCreateCryptoSessionPolicy;
  PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030  pfnCalcPrivateOpenedCryptoSessionPolicySize;
  PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030                   pfnOpenCryptoSessionPolicy;
  PFND3D12DDI_DESTROYCRYPTOSESSIONPOLICY_0030                pfnDestroyCryptoSessionPolicy;
  PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030                    pfnTransformEncryptedData;
} D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030, D3D12DDI_DEVICE_FUNCS_CONTENT_PROTECTION_STREAMING_0030;
````


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


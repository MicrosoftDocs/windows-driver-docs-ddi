---
UID: NC:d3d12umddi.PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030
title: PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030
author: windows-driver-content
description: Used to open a crypto session policy.
old-location: display\pfnd3d12ddi_opencryptosessionpolicy_0030.htm
old-project: display
ms.assetid: 24B30BE0-9B7E-4946-8677-E3E727A63498
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030, PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030, display.pfnd3d12ddi_opencryptosessionpolicy_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030 callback


## -description


Used to open a crypto session policy.


## -prototype


````
HRESULT APIENTRY* PFND3D12DDI_OPENCRYPTOSESSIONPOLICY_0030(
             D3D12DDI_HDEVICE                            hDrvDevice,
  _In_ const D3D12DDIARG_OPEN_CRYPTO_SESSION_POLICY_0030 *pArgs,
             D3D12DDI_HCRYPTOSESSIONPOLICY_0030           hDrvCryptoSessionPolicy
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to open a crypto session policy.


### -param hDrvCryptoSessionPolicy

The crypto session policy.


## -returns



Returns STATUS_SUCCESS if completed successfully.




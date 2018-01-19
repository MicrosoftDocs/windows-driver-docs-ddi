---
UID: NC:d3d12umddi.PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030
title: PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030
author: windows-driver-content
description: Used to transform encrypted data.
old-location: display\pfnd3d12ddi_transformencrypteddata_0030.htm
old-project: display
ms.assetid: B738C096-E821-4D7E-A713-47300E4E3779
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030 callback



## -description
Used to transform encrypted data.



## -prototype

````
HRESULT APIENTRY* PFND3D12DDI_TRANSFORMENCRYPTEDDATA_0030(
             D3D12DDI_HDEVICE                                        hDrvDevice,
             D3D12DDI_CRYPTO_SESSION_TRANSFORM_OPERATION_0030        Operation,
  _In_ const D3D12DDI_CRYPTO_SESSION_TRANSFORM_OUTPUT_ARGUMENTS_0030 *pOutputArguments,
  _In_ const D3D12DDI_CRYPTO_SESSION_TRANSFORM_INPUT_ARGUMENTS_0030  *pInputArguments
);
````


## -parameters

### -param hDrvDevice 

The device being processed.


### -param Operation 

The transform operation being performed.


### -param pOutputArguments [in]

The output arguments for the transform being performed.


### -param pInputArguments [in]

The input arguments for the transform being performed.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks

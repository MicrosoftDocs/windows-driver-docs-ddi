---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
title: PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
author: windows-driver-content
description: Used to create a protected resource session.
old-location: display\pfnd3d12ddi_createprotectedresourcesession_0030.htm
old-project: display
ms.assetid: CE866047-61AD-4F4C-9990-76CE6B7BC4AA
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
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
req.alt-api: PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
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

# PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030 callback



## -description
Used to create a protected resource session.



## -prototype

````
HRESULT APIENTRY* PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030(
             D3D12DDI_HDEVICE                                   hDrvDevice,
  _In_ const D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 *pArgs,
             D3D12DDI_HPROTECTEDRESOURCESESSION_0030            hDrvProtectedResourceSession,
             D3D12DDI_HRTPROTECTEDSESSION_0030                  hRtProtectedSession
);
````


## -parameters

### -param hDrvDevice 

The hardware device being processed.


### -param pArgs [in]

The arguments used to create a protected resource session.


### -param hDrvProtectedResourceSession 

The protected resource session.


### -param hRtProtectedSession 

The protected session.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks

---
UID: NC:d3d12umddi.PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030
title: PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030
author: windows-driver-content
description: Used to open a protected resource session.
old-location: display\pfnd3d12ddi_openprotectedresourcesession_0030.htm
old-project: display
ms.assetid: B71FD65C-5D10-4486-A6F7-C6EF1A4DEF03
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_openprotectedresourcesession_0030, PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030 callback function [Display Devices], PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030, d3d12umddi/PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030 callback


## -description


Used to open a protected resource session.


## -prototype


````
HRESULT APIENTRY* PFND3D12DDI_OPENPROTECTEDRESOURCESESSION_0030(
             D3D12DDI_HDEVICE                                 hDrvDevice,
  _In_ const D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 *pArgs,
             D3D12DDI_HPROTECTEDRESOURCESESSION_0030          hDrvProtectedResourceSession
);
````


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to open a protected resource session.


### -param hDrvProtectedResourceSession

The protected resource session.


## -returns



Returns STATUS_SUCCESS if completed successfully.




---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
title: PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
author: windows-driver-content
description: Used to calculate the size of a protected resource session.
old-location: display\pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0030.htm
old-project: display
ms.assetid: 3D677BE9-32D7-4EA4-988F-83A64CFA3FFC
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
req.alt-api: PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
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

# PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030 callback



## -description
Used to calculate the size of a protected resource session.



## -prototype

````
SIZE_T APIENTRY* PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030(
             D3D12DDI_HDEVICE                                 hDrvDevice,
  _In_ const D3D12DDIARG_OPEN_PROTECTED_RESOURCE_SESSION_0030 *pArgs
);
````


## -parameters

### -param hDrvDevice 

The hardware device being processed.


### -param pArgs [in]

The arguments used to open a protected resource session.


## -returns
Returns the size of the session in bytes.


## -remarks

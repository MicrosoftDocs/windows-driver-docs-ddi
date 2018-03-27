---
UID: NC:d3d12umddi.PFND3D12DDI_CREATECRYPTOSESSION_0030
title: PFND3D12DDI_CREATECRYPTOSESSION_0030
author: windows-driver-content
description: Used to create a crypto session.
old-location: display\pfnd3d12ddi_createcryptosession_0030.htm
old-project: display
ms.assetid: 3AA323B1-C4A3-4630-A664-69FB3E5C6456
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_CREATECRYPTOSESSION_0030, PFND3D12DDI_CREATECRYPTOSESSION_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATECRYPTOSESSION_0030, display.pfnd3d12ddi_createcryptosession_0030
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
-	PFND3D12DDI_CREATECRYPTOSESSION_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATECRYPTOSESSION_0030 callback


## -description


Used to create a crypto session.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to create a crypto session.


### -param hDrvCryptoSession

Used to create a crypto session.


### -param hRtProtectedSession

Used to create a protected session.


## -returns



Returns STATUS_SUCCESS if completed successfully.




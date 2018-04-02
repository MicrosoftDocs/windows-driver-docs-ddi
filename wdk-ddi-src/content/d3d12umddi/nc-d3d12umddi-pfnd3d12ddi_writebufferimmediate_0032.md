---
UID: NC:d3d12umddi.PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
title: PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
author: windows-driver-content
description: Used to create a write buffer.
old-location: display\pfnd3d12ddi_writebufferimmediate_0032.htm
old-project: display
ms.assetid: 73486EA4-F1D8-4649-81C8-1698E1854DED
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032, PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback function [Display Devices], d3d12umddi/PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032, display.pfnd3d12ddi_writebufferimmediate_0032
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
-	PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_WRITEBUFFERIMMEDIATE_0032 callback


## -description


Used to create a write buffer. 


## -parameters




### -param Arg1


### -param Count

The count.


### -param *pParams [in]

The parameters for the write buffer.


### -param *pModes [in]

The modes for the write buffer.


#### - hDrvCommandList

The command list.


## -returns



This callback function does not return a value.




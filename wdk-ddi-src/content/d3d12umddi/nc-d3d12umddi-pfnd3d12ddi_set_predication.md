---
UID: NC:d3d12umddi.PFND3D12DDI_SET_PREDICATION
title: PFND3D12DDI_SET_PREDICATION
author: windows-driver-content
description: The pfnSetPredication callback function denotes that subsequent video operations and resource manipulation commands are not actually performed if the resulting predicate data of the predicate is equal to the operation specified.
old-location: display\pfnd3d12ddi_set_predication.htm
old-project: display
ms.assetid: C5830688-4FC6-4D3F-82EB-15354B28C5F1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_SET_PREDICATION, d3d12umddi/pfnSetPredication, display.pfnd3d12ddi_set_predication, pfnSetPredication, pfnSetPredication callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
api_name:
-	pfnSetPredication
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_SET_PREDICATION callback


## -description


The <i>pfnSetPredication</i> callback function denotes that subsequent video operations and resource manipulation commands are not actually performed if the resulting predicate data of the predicate is equal to the operation specified.


## -prototype


````
PFND3D12DDI_SET_PREDICATION pfnSetPredication;

VOID APIENTRY* pfnSetPredication(
   D3D12DDI_HCOMMANDLIST   hCommandList,
   D3D12DDI_HRESOURCE      hResource,
   UINT64                  Uint64,
   D3D12DDI_PREDICATION_OP PredicationOp
)
{ ... }
````


## -parameters




### -param D3D12DDI_HCOMMANDLIST


### -param D3D12DDI_HRESOURCE


### -param UINT64


### -param D3D12DDI_PREDICATION_OP








#### - PredicationOp

A predication operation. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_predication_op.md">D3D12DDI_PREDICATION_OP</a> enumeration.


#### - Uint64

An integer.


#### - hCommandList

The handle of a command list.


#### - hResource

The handle of a resource.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_predication_op.md">D3D12DDI_PREDICATION_OP</a>



 

 



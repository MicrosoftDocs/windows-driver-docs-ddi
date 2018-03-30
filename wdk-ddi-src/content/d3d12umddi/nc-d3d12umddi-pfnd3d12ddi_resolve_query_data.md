---
UID: NC:d3d12umddi.PFND3D12DDI_RESOLVE_QUERY_DATA
title: PFND3D12DDI_RESOLVE_QUERY_DATA
author: windows-driver-content
description: The pfnResolveQueryData callback function transforms a previously stored query into an API defined format.
old-location: display\pfnd3d12ddi_resolve_query_data.htm
old-project: display
ms.assetid: 981053FF-9928-442F-B3B3-3B89AC61EEE4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_RESOLVE_QUERY_DATA, d3d12umddi/pfnResolveQueryData, display.pfnd3d12ddi_resolve_query_data, pfnResolveQueryData, pfnResolveQueryData callback function [Display Devices]
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
-	pfnResolveQueryData
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_RESOLVE_QUERY_DATA callback


## -description


The <i>pfnResolveQueryData</i> callback function transforms a previously stored query into an API defined format.


## -parameters




### -param Arg1


### -param Arg2


### -param Arg3


### -param StartElement

The value of the start element.


### -param ElementCount

The element count.


### -param hDrvDestinationBuffer

The handle of a destination buffer.


### -param DestinationOffset

The destination offset.


#### - QueryType

A query type.


#### - hCommandList

The handle of a command list.


#### - hQueryHeap

The handle of a query heap.


## -returns



This callback function does not return a value.




## -remarks



Resolve functionality is used by applications to transform a query result previously stored in a query heap into the API defined format.  The resolved data is stored in a buffer.  The results can then be consumed by a shader, predication, or mapped and read on the CPU.




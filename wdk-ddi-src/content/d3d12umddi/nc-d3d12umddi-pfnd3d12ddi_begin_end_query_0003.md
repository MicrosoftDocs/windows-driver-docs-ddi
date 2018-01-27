---
UID: NC:d3d12umddi.PFND3D12DDI_BEGIN_END_QUERY_0003
title: PFND3D12DDI_BEGIN_END_QUERY_0003
author: windows-driver-content
description: The pfnBeginQuery callback function defines the beginning of the portion of a command list to which a query applies.
old-location: display\pfnd3d12ddi_begin_end_query_0003.htm
old-project: display
ms.assetid: 9EBF7E0C-BF6D-4E99-B289-8C6581A2DEA5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3d12ddi_begin_end_query_0003, pfnBeginQuery callback function [Display Devices], pfnBeginQuery, PFND3D12DDI_BEGIN_END_QUERY_0003, PFND3D12DDI_BEGIN_END_QUERY_0003, d3d12umddi/pfnBeginQuery
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	D3d12umddi.h
apiname: 
-	pfnBeginQuery
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_BEGIN_END_QUERY_0003 callback


## -description


The <i>pfnBeginQuery</i> callback function defines the beginning of the portion of a command list to which a query applies.


## -prototype


````
PFND3D12DDI_BEGIN_END_QUERY_0003 pfnBeginQuery;

VOID  APIENTRY* pfnBeginQuery(
   D3D12DDI_HCOMMANDLIST hCommandList,
   D3D12DDI_HQUERYHEAP   hQueryHeap,
   D3D12DDI_QUERY_TYPE   QueryType,
   UINT                  StartElement
)
{ ... }
````


## -parameters




### -param D3D12DDI_HCOMMANDLIST



### -param D3D12DDI_HQUERYHEAP



### -param D3D12DDI_QUERY_TYPE



### -param UINT






#### - hQueryHeap

The handle of a query heap, which represents an array of query results.


#### - StartElement

The value of the start element.


#### - hCommandList

The handle of a command list for which to query. 


#### - QueryType

The type of query.


## -returns


This callback function does not return a value.



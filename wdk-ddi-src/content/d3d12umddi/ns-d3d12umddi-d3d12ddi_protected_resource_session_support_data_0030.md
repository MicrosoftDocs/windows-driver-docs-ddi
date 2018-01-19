---
UID: NS:d3d12umddi.D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030
title: D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030
author: windows-driver-content
description: Protected resource session support data.
old-location: display\d3d12ddi-protected-resource-session-support-data-0030.htm
old-project: display
ms.assetid: 7e8b824b-b6a6-486a-abb7-545d5156a94a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030, D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030
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
req.typenames: D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030
---

# D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030 structure



## -description
Protected resource session support data.



## -syntax

````
typedef struct _D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030 {
  UINT                                                    NodeIndex;
  D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_FLAGS_0030  Support;
} D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030, D3D12DDI_PROTECTED_RESOURCE_SESSION_SUPPORT_DATA_0030;
````


## -struct-fields

### -field NodeIndex

Node index.


### -field Support

Support.


## -remarks

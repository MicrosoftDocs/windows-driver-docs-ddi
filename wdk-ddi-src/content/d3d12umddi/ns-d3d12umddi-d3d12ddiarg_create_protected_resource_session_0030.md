---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030
title: D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030
author: windows-driver-content
description: Creates a protected resource session.
old-location: display\d3d12ddiarg-create-protected-resource-session-0030.htm
old-project: display
ms.assetid: 0b28ea12-1182-4be6-83f3-850172cc6a89
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddiarg-create-protected-resource-session-0030, D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030, D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030
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
-	HeaderDef
apilocation: 
-	d3d12umddi.h
apiname: 
-	D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030
---

# D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 structure


## -description


Creates a protected resource session.


## -syntax


````
typedef struct _D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 {
  UINT  NodeMask;
} D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030, D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030;
````


## -struct-fields




### -field NodeMask

Represents the set of nodes.


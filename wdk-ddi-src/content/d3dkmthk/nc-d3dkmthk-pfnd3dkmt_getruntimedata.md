---
UID: NC:d3dkmthk.PFND3DKMT_GETRUNTIMEDATA
title: PFND3DKMT_GETRUNTIMEDATA
author: windows-driver-content
description: The D3DKMTGetRuntimeData function is for system use only.
old-location: display\d3dkmtgetruntimedata.htm
old-project: display
ms.assetid: a73ebde8-a1d5-4f97-8457-1f01244bb266
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMTGetRuntimeData, D3DKMTGetRuntimeData callback function [Display Devices], OpenGL_Functions_c2273a4f-9a28-41b5-97c2-daa8eaa9f128.xml, PFND3DKMT_GETRUNTIMEDATA, d3dkmthk/D3DKMTGetRuntimeData, display.d3dkmtgetruntimedata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmthk.h
apiname:
-	D3DKMTGetRuntimeData
product: Windows
targetos: Windows
req.typenames: DXGK_TARGETMODE_DETAIL_TIMING
---

# PFND3DKMT_GETRUNTIMEDATA callback


## -description


The <b>D3DKMTGetRuntimeData</b> function is for system use only.


## -prototype


````
NTSTATUS APIENTRY D3DKMTGetRuntimeData(
  _Inout_ const D3DKMT_GETRUNTIMEDATA *pData
);
````


## -parameters




### -param *








#### - pData [in, out]

Reserved for system use.


## -remarks



This function is reserved for system use.




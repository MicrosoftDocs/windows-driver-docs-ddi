---
UID: NC:d3dumddi.PFND3DDDI_MULTIPLYTRANSFORM
title: PFND3DDDI_MULTIPLYTRANSFORM
author: windows-driver-content
description: The MultiplyTransform function modifies the current transform.
old-location: display\multiplytransform.htm
old-project: display
ms.assetid: 69d94062-5655-4d49-a116-7fa7e2b51a91
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: MultiplyTransform, MultiplyTransform callback function [Display Devices], PFND3DDDI_MULTIPLYTRANSFORM, UserModeDisplayDriver_Functions_4058eef2-8ccd-46e2-ad8d-fd0905811651.xml, d3dumddi/MultiplyTransform, display.multiplytransform
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	MultiplyTransform
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_MULTIPLYTRANSFORM callback


## -description


The <i>MultiplyTransform</i> function modifies the current transform.


## -prototype


````
PFND3DDDI_MULTIPLYTRANSFORM MultiplyTransform;

__checkReturn HRESULT APIENTRY MultiplyTransform(
  _In_       HANDLE                      hDevice,
  _In_ const D3DDDIARG_MULTIPLYTRANSFORM *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_multiplytransform.md">D3DDDIARG_MULTIPLYTRANSFORM</a> structure that describes how to modify the current transform.


## -returns



<i>MultiplyTransform</i> returns S_OK or an appropriate error result if the transform is not successfully modified.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_multiplytransform.md">D3DDDIARG_MULTIPLYTRANSFORM</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



 

 



---
UID: NC:d3dumddi.PFND3DDDI_SETSTREAMSOURCEUM
title: PFND3DDDI_SETSTREAMSOURCEUM
author: windows-driver-content
description: The SetStreamSourceUM function binds a vertex stream source to a user memory buffer.
old-location: display\setstreamsourceum.htm
old-project: display
ms.assetid: 75a70801-0338-45ed-a691-5f84202575d5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETSTREAMSOURCEUM, SetStreamSourceUM, SetStreamSourceUM callback function [Display Devices], UserModeDisplayDriver_Functions_0bea09c2-3bd9-4c60-9688-1c5a687e0dc9.xml, d3dumddi/SetStreamSourceUM, display.setstreamsourceum
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
-	SetStreamSourceUM
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETSTREAMSOURCEUM callback


## -description


The <i>SetStreamSourceUM</i> function binds a vertex stream source to a user memory buffer. 


## -prototype


````
PFND3DDDI_SETSTREAMSOURCEUM SetStreamSourceUM;

__checkReturn HRESULT APIENTRY SetStreamSourceUM(
  _In_       HANDLE                      hDevice,
  _In_ const D3DDDIARG_SETSTREAMSOURCEUM *pData,
  _In_ const VOID                        *pUMBuffer
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setstreamsourceum.md">D3DDDIARG_SETSTREAMSOURCEUM</a> structure that specifies the vertex stream source to bind.


#### - pUMBuffer [in]

 A pointer to the user-memory buffer that supplies the vertex data for the vertex stream source.


## -returns



<i>SetStreamSourceUM</i> returns S_OK or an appropriate error result if the vertex stream source is not successfully bound.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_setstreamsourceum.md">D3DDDIARG_SETSTREAMSOURCEUM</a>



 

 



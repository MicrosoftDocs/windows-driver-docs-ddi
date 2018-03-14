---
UID: NC:d3dumddi.PFND3DDDI_SETZRANGE
title: PFND3DDDI_SETZRANGE
author: windows-driver-content
description: The SetZRange function informs the driver about the range of z values.
old-location: display\setzrange.htm
old-project: display
ms.assetid: 29ccde7c-801c-4e90-bc39-8581f262cc65
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETZRANGE, SetZRange, SetZRange callback function [Display Devices], UserModeDisplayDriver_Functions_1f472784-89a0-4ddf-ae47-ee891774d03e.xml, d3dumddi/SetZRange, display.setzrange
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
-	SetZRange
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETZRANGE callback


## -description


The <i>SetZRange</i> function informs the driver about the range of z values.


## -prototype


````
PFND3DDDI_SETZRANGE SetZRange;

__checkReturn HRESULT APIENTRY SetZRange(
  _In_       HANDLE           hDevice,
  _In_ const D3DDDIARG_ZRANGE *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_zrange.md">D3DDDIARG_ZRANGE</a> structure that specifies minimum and maximum values for the range of z values.


## -returns



<i>SetZRange</i> returns S_OK or an appropriate error result if the driver is not successfully informed about the range of z values.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_zrange.md">D3DDDIARG_ZRANGE</a>



 

 



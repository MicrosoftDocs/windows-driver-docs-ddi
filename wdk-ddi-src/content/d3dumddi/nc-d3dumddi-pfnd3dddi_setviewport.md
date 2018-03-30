---
UID: NC:d3dumddi.PFND3DDDI_SETVIEWPORT
title: PFND3DDDI_SETVIEWPORT
author: windows-driver-content
description: The SetViewport function informs guard-band-aware drivers of the view-clipping rectangle.
old-location: display\setviewport.htm
old-project: display
ms.assetid: ef0847a3-d4f5-4a9e-a041-1b8f8523fdf7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_SETVIEWPORT, SetViewport, SetViewport callback function [Display Devices], UserModeDisplayDriver_Functions_6b0d00a2-6316-4ac0-878c-e8554e92ef57.xml, d3dumddi/SetViewport, display.setviewport
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
-	SetViewport
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_SETVIEWPORT callback


## -description


The <i>SetViewport</i> function informs guard-band-aware drivers of the view-clipping rectangle.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff544116">D3DDDIARG_VIEWPORTINFO</a> structure that describes the view-clipping rectangle.


## -returns



<i>SetViewport</i> returns S_OK or an appropriate error result if the driver is not successfully informed about the view-clipping rectangle.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544116">D3DDDIARG_VIEWPORTINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


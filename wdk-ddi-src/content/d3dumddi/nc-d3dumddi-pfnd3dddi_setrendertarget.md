---
UID: NC:d3dumddi.PFND3DDDI_SETRENDERTARGET
title: PFND3DDDI_SETRENDERTARGET
author: windows-driver-content
description: The SetRenderTarget function sets the render target surface.
old-location: display\setrendertarget.htm
old-project: display
ms.assetid: 067378bd-a2d8-4c83-9436-531519eadaa3
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DDDI_SETRENDERTARGET, PFND3DDDI_SETRENDERTARGET callback, SetRenderTarget, SetRenderTarget callback function [Display Devices], UserModeDisplayDriver_Functions_c6c2e714-ac5c-4106-98da-1d87a322c652.xml, d3dumddi/SetRenderTarget, display.setrendertarget
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
-	SetRenderTarget
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETRENDERTARGET callback function


## -description


The <i>SetRenderTarget</i> function sets the render target surface.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543347">D3DDDIARG_SETRENDERTARGET</a> structure that describes the render target surface.


## -returns



<i>SetRenderTarget</i> returns S_OK or an appropriate error result if the render target surface is not successfully set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543347">D3DDDIARG_SETRENDERTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


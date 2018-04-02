---
UID: NC:d3dumddi.PFND3DDDI_DRAWINDEXEDPRIMITIVE
title: PFND3DDDI_DRAWINDEXEDPRIMITIVE
author: windows-driver-content
description: The DrawIndexedPrimitive function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.
old-location: display\drawindexedprimitive.htm
old-project: display
ms.assetid: 12bb6274-d042-43bb-b9f5-1417f42da729
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DrawIndexedPrimitive, DrawIndexedPrimitive callback function [Display Devices], PFND3DDDI_DRAWINDEXEDPRIMITIVE, UserModeDisplayDriver_Functions_427fa7b5-5b52-4314-b097-aea6d27cb535.xml, d3dumddi/DrawIndexedPrimitive, display.drawindexedprimitive
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
-	DrawIndexedPrimitive
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DRAWINDEXEDPRIMITIVE callback


## -description


The <b>DrawIndexedPrimitive</b> function draws indexed primitives that the Microsoft Direct3D runtime has not transformed the index data in.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param *








#### - pData [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543048">D3DDDIARG_DRAWINDEXEDPRIMITIVE</a> structure that describes the indexed primitive to draw.


## -returns



<b>DrawIndexedPrimitive</b> returns S_OK or an appropriate error result if the indexed primitive is not successfully drawn.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543048">D3DDDIARG_DRAWINDEXEDPRIMITIVE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/f12af70c-a6f2-42da-be62-1cfeb90b6239">DrawIndexedPrimitive2</a>
 

 


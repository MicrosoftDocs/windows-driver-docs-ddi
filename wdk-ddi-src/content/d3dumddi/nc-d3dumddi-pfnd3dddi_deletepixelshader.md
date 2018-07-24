---
UID: NC:d3dumddi.PFND3DDDI_DELETEPIXELSHADER
title: PFND3DDDI_DELETEPIXELSHADER
author: windows-driver-content
description: The DeletePixelShader function cleans up driver-side resources that are associated with pixel shader code.
old-location: display\deletepixelshader.htm
tech.root: display
ms.assetid: bc987531-d402-4f3b-a4e2-d71fe97f5400
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DeletePixelShader, DeletePixelShader callback function [Display Devices], PFND3DDDI_DELETEPIXELSHADER, PFND3DDDI_DELETEPIXELSHADER callback, UserModeDisplayDriver_Functions_2994cbd5-2661-40e3-bdcd-3b2bfc209c24.xml, d3dumddi/DeletePixelShader, display.deletepixelshader
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
-	DeletePixelShader
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DELETEPIXELSHADER callback function


## -description


The <b>DeletePixelShader</b> function cleans up driver-side resources that are associated with pixel shader code.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param Arg1








#### - hShaderHandle [in]

 A handle to the pixel shader code object.


## -returns



<b>DeletePixelShader</b> returns S_OK or an appropriate error result if the pixel shader code object is not successfully cleaned up.




## -remarks



The <b>DeletePixelShader</b> function notifies the driver about the deletion of the pixel shader code object that the <a href="https://msdn.microsoft.com/b80a1823-6d91-440f-89e4-f7248579cc8f">CreatePixelShader</a> function created. The driver can then clean up any driver-side resources that are associated with the pixel shader code.




## -see-also




<a href="https://msdn.microsoft.com/b80a1823-6d91-440f-89e4-f7248579cc8f">CreatePixelShader</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


---
UID: NC:d3dumddi.PFND3DDDI_DESTROYLIGHT
title: PFND3DDDI_DESTROYLIGHT
description: The DestroyLight function deactivates a light source.
old-location: display\destroylight.htm
tech.root: display
ms.assetid: dbc86e4d-a002-4270-a3c4-02d16972c921
ms.date: 05/10/2018
ms.keywords: DestroyLight, DestroyLight callback function [Display Devices], PFND3DDDI_DESTROYLIGHT, PFND3DDDI_DESTROYLIGHT callback, UserModeDisplayDriver_Functions_fce83d93-bfe6-44f9-a1c4-ea92921bfb69.xml, d3dumddi/DestroyLight, display.destroylight
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
-	DestroyLight
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DESTROYLIGHT callback function


## -description


The <b>DestroyLight</b> function deactivates a light source.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543034">D3DDDIARG_DESTROYLIGHT</a> structure that describes how to set the light source.


## -returns



<b>DestroyLight</b> returns S_OK or an appropriate error result if the light source is not successfully deactivated.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543034">D3DDDIARG_DESTROYLIGHT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


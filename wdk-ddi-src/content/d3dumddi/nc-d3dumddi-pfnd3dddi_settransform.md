---
UID: NC:d3dumddi.PFND3DDDI_SETTRANSFORM
title: PFND3DDDI_SETTRANSFORM
author: windows-driver-content
description: The SetTransform function sets up a transform.
old-location: display\settransform.htm
tech.root: display
ms.assetid: 0e989ea4-3693-4c0b-86a5-96b865a0193f
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_SETTRANSFORM, PFND3DDDI_SETTRANSFORM callback, SetTransform, SetTransform callback function [Display Devices], UserModeDisplayDriver_Functions_721be745-bcea-4eeb-9bd4-ddda1f1912a5.xml, d3dumddi/SetTransform, display.settransform
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
-	SetTransform
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETTRANSFORM callback function


## -description


The <i>SetTransform</i> function sets up a transform.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543367">D3DDDIARG_SETTRANSFORM</a> structure that describes how to set up the transform.


## -returns



<i>SetTransform</i> returns S_OK or an appropriate error result if the transform is not successfully set up.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543367">D3DDDIARG_SETTRANSFORM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


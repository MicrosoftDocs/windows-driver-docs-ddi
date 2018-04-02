---
UID: NC:d3d10umddi.PFND3D10DDI_GENMIPS
title: PFND3D10DDI_GENMIPS
author: windows-driver-content
description: The GenMips function generates the lower MIP-map levels on the specified shader-resource view.
old-location: display\genmips.htm
old-project: display
ms.assetid: abd045f2-9c05-4579-8d80-aba31523157d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: GenMips, GenMips callback function [Display Devices], PFND3D10DDI_GENMIPS, UserModeDisplayDriverDx10_Functions_56ecca1c-6b70-4ed8-9831-aec5fa5416cf.xml, d3d10umddi/GenMips, display.genmips
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	GenMips
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_GENMIPS callback


## -description


The <i>GenMips</i> function generates the lower MIP-map levels on the specified shader-resource view. 


## -parameters




### -param Arg1


### -param Arg2








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - hShaderResourceView [in]

 A handle to the MIP-map texture surface.


## -returns



None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_FAIL if the base resource was not created with the appropriate flags or can set E_INVALIDARG if the MIP type was incorrectly specified.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 


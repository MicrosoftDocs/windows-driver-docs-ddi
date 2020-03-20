---
UID: NC:d3d10umddi.PFND3D10DDI_GENMIPS
title: PFND3D10DDI_GENMIPS (d3d10umddi.h)
description: The GenMips function generates the lower MIP-map levels on the specified shader-resource view.
old-location: display\genmips.htm
ms.assetid: abd045f2-9c05-4579-8d80-aba31523157d
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_GENMIPS callback function"]
ms.keywords: GenMips, GenMips callback function [Display Devices], PFND3D10DDI_GENMIPS, PFND3D10DDI_GENMIPS callback, UserModeDisplayDriverDx10_Functions_56ecca1c-6b70-4ed8-9831-aec5fa5416cf.xml, d3d10umddi/GenMips, display.genmips
f1_keywords:
 - "d3d10umddi/GenMips"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- GenMips
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_GENMIPS callback function


## -description


The <i>GenMips</i> function generates the lower MIP-map levels on the specified shader-resource view. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hShaderResourceView* [in]

A handle to the MIP-map texture surface.


## -remarks




The driver can use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. The driver can set E_FAIL if the base resource was not created with the appropriate flags or can set E_INVALIDARG if the MIP type was incorrectly specified.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>
 

 


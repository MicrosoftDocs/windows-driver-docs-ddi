---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEQUERYSIZE
title: PFND3D10DDI_CALCPRIVATEQUERYSIZE
author: windows-driver-content
description: The CalcPrivateQuerySize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.
old-location: display\calcprivatequerysize.htm
ms.assetid: 59a59aa8-085e-4bf8-8a6f-e08f2aecd894
ms.date: 5/10/2018
ms.keywords: CalcPrivateQuerySize, CalcPrivateQuerySize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEQUERYSIZE, PFND3D10DDI_CALCPRIVATEQUERYSIZE callback, UserModeDisplayDriverDx10_Functions_79c9e2a9-e27e-4bd8-bc45-20dd14f0627a.xml, d3d10umddi/CalcPrivateQuerySize, display.calcprivatequerysize
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
-	CalcPrivateQuerySize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CALCPRIVATEQUERYSIZE callback function


## -description


The <b>CalcPrivateQuerySize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a query.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateQuery* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541685">D3D10DDIARG_CREATEQUERY</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateQuerySize</b> returns the size of the memory region that the driver requires for creating a query.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541685">D3D10DDIARG_CREATEQUERY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 


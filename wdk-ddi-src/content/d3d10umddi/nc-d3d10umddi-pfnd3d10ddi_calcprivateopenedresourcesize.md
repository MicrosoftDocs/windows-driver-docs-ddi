---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE
title: PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE
author: windows-driver-content
description: The CalcPrivateOpenedResourceSize function determines the size of the user-mode display driver's private shared region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an opened resource.
old-location: display\calcprivateopenedresourcesize.htm
ms.assetid: 000688fb-6475-4dab-bb65-91c899a592a7
ms.date: 5/10/2018
ms.keywords: CalcPrivateOpenedResourceSize, CalcPrivateOpenedResourceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE, PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE callback, UserModeDisplayDriverDx10_Functions_1be7ba80-5ffc-4871-b687-f12b4a81fad0.xml, d3d10umddi/CalcPrivateOpenedResourceSize, display.calcprivateopenedresourcesize
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
-	CalcPrivateOpenedResourceSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE callback function


## -description


The <b>CalcPrivateOpenedResourceSize</b> function determines the size of the user-mode display driver's private shared region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an opened resource.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pOpenResource* [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541736">D3D10DDIARG_OPENRESOURCE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the shared memory region. 


## -returns



<b>CalcPrivateOpenedResourceSize</b> returns the size of the shared memory region that the driver requires for opening resources.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541736">D3D10DDIARG_OPENRESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>
 

 


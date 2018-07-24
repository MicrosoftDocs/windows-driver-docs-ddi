---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
title: PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
author: windows-driver-content
description: The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.
old-location: display\calcprivatecommandlistsize.htm
tech.root: display
ms.assetid: 04725df2-6373-4e04-862e-d533363af00b
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateCommandListSize, CalcPrivateCommandListSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE, PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback, UserModeDisplayDriverDx11_Functions_ba8c13ec-47a3-4d4a-9356-59c9a3edd34d.xml, d3d10umddi/CalcPrivateCommandListSize, display.calcprivatecommandlistsize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateCommandListSize is supported beginning with the Windows 7 operating system.
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
-	CalcPrivateCommandListSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback function


## -description


The <b>CalcPrivateCommandListSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateCommandList [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542040">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


## -returns



<b>CalcPrivateCommandListSize</b> returns the size of the memory region that the driver requires to create a command list.




## -remarks



The driver is only required to implement <b>CalcPrivateCommandListSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a> function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542040">D3D11DDIARG_CREATECOMMANDLIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542163">D3D11DDI_THREADING_CAPS</a>



<a href="https://msdn.microsoft.com/83cd5f34-5f12-4ead-ad33-366fc3c6e804">GetCaps(D3D10_2)</a>
 

 


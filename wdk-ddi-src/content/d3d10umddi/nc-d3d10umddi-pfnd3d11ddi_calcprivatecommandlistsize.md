---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE
title: PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE (d3d10umddi.h)
description: The CalcPrivateCommandListSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.
old-location: display\calcprivatecommandlistsize.htm
ms.assetid: 04725df2-6373-4e04-862e-d533363af00b
ms.date: 05/10/2018
ms.keywords: CalcPrivateCommandListSize, CalcPrivateCommandListSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE, PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback, UserModeDisplayDriverDx11_Functions_ba8c13ec-47a3-4d4a-9356-59c9a3edd34d.xml, d3d10umddi/CalcPrivateCommandListSize, display.calcprivatecommandlistsize
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- CalcPrivateCommandListSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CALCPRIVATECOMMANDLISTSIZE callback function


## -description


The <b>CalcPrivateCommandListSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a command list.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateCommandList* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


## -returns



<b>CalcPrivateCommandListSize</b> returns the size of the memory region that the driver requires to create a command list.




## -remarks



The driver is only required to implement <b>CalcPrivateCommandListSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>
 

 


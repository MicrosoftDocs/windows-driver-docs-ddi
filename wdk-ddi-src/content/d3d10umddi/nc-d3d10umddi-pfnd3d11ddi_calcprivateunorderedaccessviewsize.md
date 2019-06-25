---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
title: PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE (d3d10umddi.h)
description: The CalcPrivateUnorderedAccessViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an unordered access view.
old-location: display\calcprivateunorderedaccessviewsize.htm
ms.assetid: 6aca5d33-c8c6-4c6b-a66a-e28a958cbc2e
ms.date: 05/10/2018
ms.keywords: CalcPrivateUnorderedAccessViewSize, CalcPrivateUnorderedAccessViewSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE, PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE callback, UserModeDisplayDriverDx11_Functions_bc7bfd55-2032-4df8-8a68-32672fe72b4b.xml, d3d10umddi/CalcPrivateUnorderedAccessViewSize, display.calcprivateunorderedaccessviewsize
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateUnorderedAccessViewSize is supported beginning with the Windows 7 operating system.
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
- CalcPrivateUnorderedAccessViewSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE callback function


## -description


The <b>CalcPrivateUnorderedAccessViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an unordered access view.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

*pCreateUnorderedAccessView* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateUnorderedAccessViewSize</b> returns the size of the memory region that the driver requires to create an unordered access view.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createunorderedaccessview">D3D11DDIARG_CREATEUNORDEREDACCESSVIEW</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>
 

 


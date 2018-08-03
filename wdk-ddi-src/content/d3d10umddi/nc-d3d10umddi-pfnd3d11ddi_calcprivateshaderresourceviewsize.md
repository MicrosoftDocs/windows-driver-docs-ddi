---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize_d3d11_.htm
tech.root: display
ms.assetid: 894f6ef1-a5a4-40aa-9a07-f66da4ce7d81
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CalcPrivateShaderResourceViewSize, CalcPrivateShaderResourceViewSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback, UserModeDisplayDriverDx11_Functions_27936968-ec44-4c95-afb1-a3ba522ad8f6.xml, d3d10umddi/CalcPrivateShaderResourceViewSize, display.calcprivateshaderresourceviewsize_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateShaderResourceViewSize(D3D11) is supported beginning with the Windows 7 operating system.
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
-	CalcPrivateShaderResourceViewSize
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function


## -description


The <b>CalcPrivateShaderResourceViewSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.


## -parameters




### -param Arg1


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateShaderResourceView [in]

 A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateShaderResourceViewSize(D3D11)</b> returns the size of the memory region that the driver requires to create a shader resource view.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542073">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>
 

 


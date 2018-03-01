---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize_d3d11_.htm
old-project: display
ms.assetid: 894f6ef1-a5a4-40aa-9a07-f66da4ce7d81
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateShaderResourceViewSize, CalcPrivateShaderResourceViewSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, UserModeDisplayDriverDx11_Functions_27936968-ec44-4c95-afb1-a3ba522ad8f6.xml, d3d10umddi/CalcPrivateShaderResourceViewSize, display.calcprivateshaderresourceviewsize_d3d11_
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
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback


## -description


The <b>CalcPrivateShaderResourceViewSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.


## -prototype


````
PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE CalcPrivateShaderResourceViewSize;

SIZE_T APIENTRY CalcPrivateShaderResourceViewSize(
  _In_       D3D10DDI_HDEVICE                     hDevice,
  _In_ const D3D11DDIARG_CREATESHADERRESOURCEVIEW *pCreateShaderResourceView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateShaderResourceView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateShaderResourceViewSize(D3D11)</b> returns the size of the memory region that the driver requires to create a shader resource view.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createshaderresourceview.md">D3D11DDIARG_CREATESHADERRESOURCEVIEW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATERESOURCESIZE
title: PFND3D11DDI_CALCPRIVATERESOURCESIZE
author: windows-driver-content
description: The CalcPrivateResourceSize(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).
old-location: display\calcprivateresourcesize_d3d11_.htm
old-project: display
ms.assetid: 3b3a2571-012e-4acd-b836-f52e7b88a2fb
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivateresourcesize_d3d11_, CalcPrivateResourceSize callback function [Display Devices], CalcPrivateResourceSize, PFND3D11DDI_CALCPRIVATERESOURCESIZE, PFND3D11DDI_CALCPRIVATERESOURCESIZE, d3d10umddi/CalcPrivateResourceSize, UserModeDisplayDriverDx11_Functions_85fd70d1-91ec-4b9d-b379-18b5d3d43e67.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateResourceSize(D3D11) is supported beginning with the Windows 7 operating system.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CalcPrivateResourceSize
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX"
---

# PFND3D11DDI_CALCPRIVATERESOURCESIZE callback


## -description


The <b>CalcPrivateResourceSize(D3D11)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).


## -prototype


````
PFND3D11DDI_CALCPRIVATERESOURCESIZE CalcPrivateResourceSize;

SIZE_T APIENTRY CalcPrivateResourceSize(
  _In_       D3D10DDI_HDEVICE           hDevice,
  _In_ const D3D11DDIARG_CREATERESOURCE *pCreateResource
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE



### -param *






#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateResource [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns


<b>CalcPrivateResourceSize(D3D11)</b> returns the size of the memory region that the driver requires to create resources.



## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11DDI_CALCPRIVATERESOURCESIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


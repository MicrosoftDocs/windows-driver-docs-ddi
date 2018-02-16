---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE
title: PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE
author: windows-driver-content
description: The CalcPrivateRenderTargetViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.
old-location: display\calcprivaterendertargetviewsize.htm
old-project: display
ms.assetid: 14d85e4a-960c-4438-9360-a4f2677603b8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivaterendertargetviewsize, CalcPrivateRenderTargetViewSize callback function [Display Devices], CalcPrivateRenderTargetViewSize, PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE, PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE, d3d10umddi/CalcPrivateRenderTargetViewSize, UserModeDisplayDriverDx10_Functions_48ca8f95-06ba-4a11-8517-bd4638691e65.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CalcPrivateRenderTargetViewSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback


## -description


The <b>CalcPrivateRenderTargetViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.


## -prototype


````
PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE CalcPrivateRenderTargetViewSize;

SIZE_T APIENTRY CalcPrivateRenderTargetViewSize(
  _In_       D3D10DDI_HDEVICE                   hDevice,
  _In_ const D3D10DDIARG_CREATERENDERTARGETVIEW *pCreateRenderTargetView
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pCreateRenderTargetView [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateRenderTargetViewSize</b> returns the size of the memory region that the driver requires for creating a render target view.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createrendertargetview.md">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


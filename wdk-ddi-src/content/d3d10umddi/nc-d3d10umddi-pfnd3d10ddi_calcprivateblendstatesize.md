---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
title: PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE
author: windows-driver-content
description: The CalcPrivateBlendStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.
old-location: display\calcprivateblendstatesize.htm
old-project: display
ms.assetid: c13862b0-3136-4a95-bb00-6057f2934068
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.calcprivateblendstatesize, CalcPrivateBlendStateSize callback function [Display Devices], CalcPrivateBlendStateSize, PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE, PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE, d3d10umddi/CalcPrivateBlendStateSize, UserModeDisplayDriverDx10_Functions_bb7c2ca6-61c8-4f54-a635-4ec9fb539837.xml
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
-	CalcPrivateBlendStateSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback


## -description


The <b>CalcPrivateBlendStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a blend state.


## -prototype


````
PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE CalcPrivateBlendStateSize;

SIZE_T APIENTRY CalcPrivateBlendStateSize(
  _In_       D3D10DDI_HDEVICE     hDevice,
  _In_ const D3D10_DDI_BLEND_DESC *pBlendDesc
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE


### -param *








#### - hDevice [in]

 A handle to the display device (graphics context).


#### - pBlendDesc [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_blend_desc.md">D3D10_DDI_BLEND_DESC</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region. 


## -returns



<b>CalcPrivateBlendStateSize</b> returns the size of the memory region that the driver requires for creating a blend state.




## -remarks



None.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_ddi_blend_desc.md">D3D10_DDI_BLEND_DESC</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEBLENDSTATESIZE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


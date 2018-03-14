---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEVICESIZE
title: PFND3D10DDI_CALCPRIVATEDEVICESIZE
author: windows-driver-content
description: The CalcPrivateDeviceSize function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data.
old-location: display\calcprivatedevicesize.htm
old-project: display
ms.assetid: 8221a99a-1b46-48ba-8930-ac973e009eee
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateDeviceSize, CalcPrivateDeviceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEDEVICESIZE, UserModeDisplayDriverDx10_Functions_0de51abc-5fe3-4d65-bd0a-cc4f32f08d81.xml, d3d10umddi/CalcPrivateDeviceSize, display.calcprivatedevicesize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	CalcPrivateDeviceSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_CALCPRIVATEDEVICESIZE callback


## -description


The <b>CalcPrivateDeviceSize</b> function determines the size of a memory region that the user-mode display driver requires from the Microsoft Direct3D runtime to store frequently-accessed data. 


## -prototype


````
PFND3D10DDI_CALCPRIVATEDEVICESIZE CalcPrivateDeviceSize;

SIZE_T APIENTRY CalcPrivateDeviceSize(
  _In_       D3D10DDI_HADAPTER                 hAdapter,
  _In_ const D3D10DDIARG_CALCPRIVATEDEVICESIZE *pData
)
{ ... }
````


## -parameters




### -param D3D10DDI_HADAPTER


### -param *








#### - hAdapter [in]

 A handle that identifies the graphics adapter. 


#### - pData [in]

 A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_calcprivatedevicesize.md">D3D10DDIARG_CALCPRIVATEDEVICESIZE</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


## -returns



<b>CalcPrivateDeviceSize</b> returns the size of the memory region that the driver requires to store frequently-accessed data.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_calcprivatedevicesize.md">D3D10DDIARG_CALCPRIVATEDEVICESIZE</a>



 

 



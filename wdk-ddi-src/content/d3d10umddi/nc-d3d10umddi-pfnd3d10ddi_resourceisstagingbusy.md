---
UID: NC:d3d10umddi.PFND3D10DDI_RESOURCEISSTAGINGBUSY
title: PFND3D10DDI_RESOURCEISSTAGINGBUSY (d3d10umddi.h)
description: The ResourceIsStagingBusy function determines whether a resource is currently being used by the graphics pipeline.
old-location: display\resourceisstagingbusy.htm
ms.assetid: df8498e2-a3b5-4bc8-b6d2-0d444f1d1485
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_RESOURCEISSTAGINGBUSY, PFND3D10DDI_RESOURCEISSTAGINGBUSY callback, ResourceIsStagingBusy, ResourceIsStagingBusy callback function [Display Devices], UserModeDisplayDriverDx10_Functions_4109ed72-e2a5-4b1a-bfc6-7e5ce9227efc.xml, d3d10umddi/ResourceIsStagingBusy, display.resourceisstagingbusy
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- ResourceIsStagingBusy
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_RESOURCEISSTAGINGBUSY callback function


## -description


The <i>ResourceIsStagingBusy</i> function determines whether a resource is currently being used by the graphics pipeline. 


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hResource* [in]

A handle to the resource.


## -returns



<i>ResourceIsStagingBusy</i> returns a Boolean value that specifies whether the resource that the <i>hResource</i> parameter specifies is currently being used by the graphics pipeline. <b>TRUE</b> indicates that the graphics pipeline currently uses the resource; <b>FALSE</b> indicates that the graphics pipeline currently does not use the resource. 




## -remarks



The Microsoft Direct3D runtime call to <i>ResourceIsStagingBusy</i> is roughly equivalent to the call to the <a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a> function with the D3D10_DDI_MAP_FLAG_DONOTWAIT flag set in the <i>Flags</i> parameter, except that <i>ResourceMap</i> can perform only one subresource at a time and <i>ResourceIsStagingBusy</i> can be called while some of the subresources are currently mapped. 

The user-mode display driver is not required to flush any partially built command buffer. If the driver is resident in the partially built command buffer, the driver qualifies as busy. 

<i>ResourceIsStagingBusy</i> should not encounter any errors. However, <i>ResourceIsStagingBusy</i> might call the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function for critical errors. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/1310a3f8-02dd-4d35-98ad-4016e57d1eb2">ResourceMap</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>
 

 


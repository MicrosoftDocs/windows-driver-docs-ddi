---
UID: NC:d3d10umddi.PFND3D10DDI_CLOSEADAPTER
title: PFND3D10DDI_CLOSEADAPTER
author: windows-driver-content
description: The CloseAdapter(D3D10) function releases resources for a graphics adapter object.
old-location: display\closeadapter_d3d10_.htm
old-project: display
ms.assetid: bc7ccd91-becc-4596-a56a-562cfe9a18b9
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: CloseAdapter, CloseAdapter callback function [Display Devices], PFND3D10DDI_CLOSEADAPTER, PFND3D10DDI_CLOSEADAPTER callback, UserModeDisplayDriverDx10_Functions_0adac9d0-3334-4bee-86ef-4e1450b1feb0.xml, d3d10umddi/CloseAdapter, display.closeadapter_d3d10_
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
-	CloseAdapter
product: Windows
targetos: Windows
req.typenames: 
---

# PFND3D10DDI_CLOSEADAPTER callback function


## -description


The <b>CloseAdapter(D3D10)</b> function releases resources for a graphics adapter object.


## -parameters




### -param Arg1








#### - hAdapter [in]

 A handle to the graphics adapter object that was created with the <a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a> function.


## -returns



<b>CloseAdapter(D3D10)</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. 




## -remarks



The user-mode display driver's <b>CloseAdapter(D3D10)</b> function should free all of the resources that the driver allocated for the graphics adapter object.

Before <b>CloseAdapter(D3D10)</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function will be destroyed in calls to the driver's <a href="https://msdn.microsoft.com/90ada8c8-8ad8-4992-aac1-6eb7fdf3f249">DestroyDevice(D3D10)</a> function.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541811">D3D10DDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/90ada8c8-8ad8-4992-aac1-6eb7fdf3f249">DestroyDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a>
 

 


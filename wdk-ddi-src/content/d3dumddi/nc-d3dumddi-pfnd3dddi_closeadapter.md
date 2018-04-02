---
UID: NC:d3dumddi.PFND3DDDI_CLOSEADAPTER
title: PFND3DDDI_CLOSEADAPTER
author: windows-driver-content
description: The CloseAdapter function releases resources for a graphics adapter object.
old-location: display\closeadapter.htm
old-project: display
ms.assetid: 9dc7f71a-753d-41ca-8eaa-bff6536e834f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CloseAdapter, CloseAdapter callback function [Display Devices], PFND3DDDI_CLOSEADAPTER, UserModeDisplayDriver_Functions_ccc1793f-15b1-480f-8835-38326b749308.xml, d3dumddi/CloseAdapter, display.closeadapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	CloseAdapter
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_CLOSEADAPTER callback


## -description


The <b>CloseAdapter</b> function releases resources for a graphics adapter object.


## -parameters




### -param hAdapter [in]

 A handle to the graphics adapter object that was created with the <a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a> function.


## -returns



<b>CloseAdapter</b> returns S_OK if the operation succeeds. Otherwise, this function returns an appropriate error result. 




## -remarks



The user-mode display driver's <b>CloseAdapter</b> function should free all of the resources that it allocated for the graphics adapter object.

Before <b>CloseAdapter</b> closes the graphics adapter object, all of the display devices that were created by using the graphics adapter object in calls to the user-mode display driver's <a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a> function must be destroyed in calls to the driver's <a href="https://msdn.microsoft.com/a3c158c2-6c0d-4da0-80f4-569971b10673">DestroyDevice</a> function.




## -see-also




<a href="https://msdn.microsoft.com/ce35bdac-af90-471f-af93-0e665be6c7f6">CreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544355">D3DDDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/a3c158c2-6c0d-4da0-80f4-569971b10673">DestroyDevice</a>



<a href="https://msdn.microsoft.com/41dc9ee4-e9bc-4ebd-9b90-6446ded6ea16">OpenAdapter</a>
 

 


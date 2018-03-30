---
UID: NC:d3dumddi.PFND3DDDI_DESTROYVIDEOPROCESSDEVICE
title: PFND3DDDI_DESTROYVIDEOPROCESSDEVICE
author: windows-driver-content
description: The DestroyVideoProcessDevice function releases resources for a Microsoft DirectX Video Acceleration (VA) video processing device.
old-location: display\destroyvideoprocessdevice.htm
old-project: display
ms.assetid: dc0f8dba-afdd-47f4-ba7f-72c510e80052
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DestroyVideoProcessDevice, DestroyVideoProcessDevice callback function [Display Devices], PFND3DDDI_DESTROYVIDEOPROCESSDEVICE, UserModeDisplayDriver_Functions_a10d05fa-387f-469f-b516-17378f2bd655.xml, d3dumddi/DestroyVideoProcessDevice, display.destroyvideoprocessdevice
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
-	DestroyVideoProcessDevice
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYVIDEOPROCESSDEVICE callback


## -description


The <b>DestroyVideoProcessDevice</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) video processing device.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context).


### -param hVideoProcessor [in]

 A handle to the DirectX VA video processing device that was created by the <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function.


## -returns



<b>DestroyVideoProcessDevice</b>  should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA decode device.




## -remarks



The <b>DestroyVideoProcessDevice</b> function notifies the driver to destroy the handle to the DirectX VA video processing device that the <a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a> function previously created. The driver can then release resources that are associated with the DirectX VA video processing device handle.




## -see-also




<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>
 

 


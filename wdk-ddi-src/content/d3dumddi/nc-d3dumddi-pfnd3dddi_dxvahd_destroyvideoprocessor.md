---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR
title: PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR (d3dumddi.h)
description: The DestroyVideoProcessor function releases resources for a Microsoft DirectX Video Acceleration (VA) video processor.
old-location: display\destroyvideoprocessor.htm
tech.root: display
ms.assetid: ea90fe17-4b79-4011-9e05-d5dbd06c0c6b
ms.date: 05/10/2018
ms.keywords: DestroyVideoProcessor, DestroyVideoProcessor callback function [Display Devices], PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR, PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR callback, UserModeDisplayDriver_Functions_e55b46ab-1325-4bb7-bf22-9f3cb19bff71.xml, d3dumddi/DestroyVideoProcessor, display.destroyvideoprocessor
ms.topic: callback
f1_keywords:
 - "d3dumddi/DestroyVideoProcessor"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: DestroyVideoProcessor is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DestroyVideoProcessor
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_DXVAHD_DESTROYVIDEOPROCESSOR callback function


## -description


The <b>DestroyVideoProcessor</b> function releases resources for a Microsoft DirectX Video Acceleration (VA) video processor.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the DirectX VA video processor that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a> function creates. 


## -returns



<b>DestroyVideoProcessor</b> should return S_OK or an appropriate error result if it cannot successfully release resources for the DirectX VA video processor. 




## -remarks



The <b>DestroyVideoProcessor</b> function notifies the driver to destroy the handle to the DirectX VA video processor that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a> function previously created. The driver can then release resources that are associated with the DirectX VA video processor handle.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a>
 

 


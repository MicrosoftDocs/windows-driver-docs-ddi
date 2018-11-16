---
UID: NC:d3dumddi.PFND3DDDI_CREATEDECODEDEVICE
title: PFND3DDDI_CREATEDECODEDEVICE
author: windows-driver-content
description: The CreateDecodeDevice function creates a Microsoft DirectX Video Acceleration (DirectX VA) decode device that is used to decode video.
old-location: display\createdecodedevice.htm
tech.root: display
ms.assetid: 4d9a062a-2fdf-4e55-a335-c03c5d5665ff
ms.date: 05/10/2018
ms.keywords: CreateDecodeDevice, CreateDecodeDevice callback function [Display Devices], PFND3DDDI_CREATEDECODEDEVICE, PFND3DDDI_CREATEDECODEDEVICE callback, UserModeDisplayDriver_Functions_a6618d5f-ea60-467f-bc0b-e1fe3ee268fe.xml, d3dumddi/CreateDecodeDevice, display.createdecodedevice
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
-	CreateDecodeDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_CREATEDECODEDEVICE callback function


## -description


The <b>CreateDecodeDevice</b> function creates a Microsoft DirectX Video Acceleration (DirectX VA) decode device that is used to decode video. 


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *

*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542927">D3DDDIARG_CREATEDECODEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.


## -returns



<b>CreateDecodeDevice</b> returns one of the following values:

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The DirectX VA decode device is successfully created. | 
| **E_OUTOFMEMORY** | [CreateDecodeDevice](https://msdn.microsoft.com/4d9a062a-2fdf-4e55-a335-c03c5d5665ff)  could not allocate the required memory for it to complete. | 

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542927">D3DDDIARG_CREATEDECODEDEVICE</a>



<a href="https://msdn.microsoft.com/3685e58b-8d67-4b01-a8a0-8a794d653637">DestroyDecodeDevice</a>
 

 


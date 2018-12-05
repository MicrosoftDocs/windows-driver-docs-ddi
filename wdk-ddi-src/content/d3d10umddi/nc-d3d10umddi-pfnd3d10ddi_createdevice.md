---
UID: NC:d3d10umddi.PFND3D10DDI_CREATEDEVICE
title: PFND3D10DDI_CREATEDEVICE
author: windows-driver-content
description: The CreateDevice(D3D10) function creates a graphics context that is referenced in subsequent calls.
old-location: display\createdevice_d3d10_.htm
ms.assetid: c69eedb1-c975-412c-aa9f-cf64a702f937
ms.date: 05/10/2018
ms.keywords: CreateDevice, CreateDevice callback function [Display Devices], PFND3D10DDI_CREATEDEVICE, PFND3D10DDI_CREATEDEVICE callback, UserModeDisplayDriverDx10_Functions_4d3d9d4c-e03b-46a9-a62a-cb49f071c0a2.xml, d3d10umddi/CreateDevice, display.createdevice_d3d10_
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
-	CreateDevice
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_CREATEDEVICE callback function


## -description


The <b>CreateDevice(D3D10)</b> function creates a graphics context that is referenced in subsequent calls. 


## -parameters




### -param Arg1

*hAdapter* [in]

A handle to the graphics adapter object that was created with the <a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a> function.

### -param *

*pCreateData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use.


## -returns

*CreateDevice(D3D10)* returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The graphics context was successfully created.|
|DXGI_STATUS_NO_REDIRECTION|The graphics context was successfully created. However, the DirectX Graphics Infrastructure (DXGI) should not use the shared resource presentation path to effect communication with the Desktop Windows Manager (DWM). For more information about the DXGI DDI, see [Supporting the DXGI DDI](https://docs.microsoft.com/en-us/windows-hardware/drivers/display/supporting-the-dxgi-ddi).|
|E_OUTOFMEMORY|[CreateDevice(D3D10)](https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice) could not allocate the memory that was required for it to complete.|

## -remarks

A display device is a graphics context that is used to hold a collection of rendering state. The same process can create multiple devices on a given adapter. Note that the number of display devices that can simultaneously exist is limited only by available system memory. That is, a driver cannot hardcode a maximum device limit.

Generally, devices are independent of each other, so that resources that are created in one device cannot be referenced or accessed by resources that are created in another. However, cross-process resources are an exception to this rule.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541664">D3D10DDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541811">D3D10DDI_ADAPTERFUNCS</a>



<a href="https://msdn.microsoft.com/90ada8c8-8ad8-4992-aac1-6eb7fdf3f249">DestroyDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/50c10021-2bad-4e3c-99cc-24cf31fbc95d">OpenAdapter10</a>
 

 


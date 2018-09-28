---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM
title: PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM
author: windows-driver-content
description: Creates an enumeration object for the video processor capabilities of the driver.
old-location: display\createvideoprocessorenum.htm
ms.assetid: 38c27502-7e8a-45a1-8a7c-315300502480
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: CreateVideoProcessorEnum, CreateVideoProcessorEnum callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM, PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback, d3d10umddi/CreateVideoProcessorEnum, display.createvideoprocessorenum
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	CreateVideoProcessorEnum
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11_1DDI_CREATEVIDEOPROCESSORENUM callback function


## -description


Creates an enumeration object for the video processor capabilities of the driver.


## -parameters




### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param *

pCreateData [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406316">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a> structure. This structure specifies the attributes of the video processor enumeration object to be created.

### -param Arg2

hVideoProcessorEnum [in]

A handle to the driver's private data for the video processor enumeration object. For more information, see the Remarks section.

### -param Arg3

hRTVideoProcessorEnum [in]

A handle to the video processor enumeration object that the driver should use when it calls back into the Direct3D runtime.


## -returns



<b>CreateVideoProcessorEnum</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The video processor enumeration object was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>
 




## -remarks



The Direct3D runtime calls <i>CreateVideoProcessorEnum</i> after it has called the driver's <a href="https://msdn.microsoft.com/a30d98b2-3d39-456a-8363-44ccc71e58ff">CalcPrivateVideoProcessorEnumSize </a>   to determine the size in bytes for the private data that the driver requires for the video processor enumeration object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor enumeration object.

When the runtime  calls <i>CreateVideoProcessorEnum</i>, it passes the handle to the private data memory in the <i>hVideoProcessorEnum</i> parameter. This handle is actually a pointer to the memory. 




## -see-also




<a href="https://msdn.microsoft.com/a30d98b2-3d39-456a-8363-44ccc71e58ff">CalcPrivateVideoProcessorEnumSize </a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406316">D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM</a>
 

 


---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
title: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
author: windows-driver-content
description: Used to simultaneously create a heap and resource.
old-location: display\pfnd3d12ddi_createheapandresource_0030.htm
old-project: display
ms.assetid: A6D597AA-C72A-46A5-91E8-22B225B380F2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_CREATEHEAPANDRESOURCE_0030, PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEHEAPANDRESOURCE_0030, display.pfnd3d12ddi_createheapandresource_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
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
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATEHEAPANDRESOURCE_0030
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_CREATEHEAPANDRESOURCE_0030 callback


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Used to simultaneously create a heap and resource.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param D3D12DDIARG_CREATEHEAP_0001

Arguments used to create a heap.

### -param Arg2

Used to create a heap.

### -param Arg3

Used to create a resource.

### -param Arg4

The protected resource session.

### -param Arg5

The hardware resource.


#### - d3d12ddi_clear_values [in, optional]

Used to clear the values of the resource.


#### - d3d12ddi_hdevice

The device being operated on.


#### - d3d12ddiarg_createresource_0003 [in, optional]

Arguments used to create a resource.


## -returns



Returns STATUS_SUCCESS if completed successfully.




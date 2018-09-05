---
UID: NC:d3d12umddi.PFND3D12DDI_GETPAGEABLESIZE_0020
title: PFND3D12DDI_GETPAGEABLESIZE_0020
author: windows-driver-content
description: The pfnGetPageableSize callback function gets the pageable size.
old-location: display\pfnd3d12ddi_getpageablesize.htm
ms.assetid: DC215186-A216-4C34-AE9A-A487178B34C0
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_GETPAGEABLESIZE_0020, PFND3D12DDI_GETPAGEABLESIZE_0020 callback, d3d12umddi/pfnGetPageableSize, display.pfnd3d12ddi_getpageablesize, pfnGetPageableSize, pfnGetPageableSize callback function [Display Devices]
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
req.max-support: Windows 10, version 1709
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
-	D3d12umddi.h
api_name:
-	pfnGetPageableSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_GETPAGEABLESIZE_0020 callback function


## -description


The <i>pfnGetPageableSize</i> callback function gets the pageable size.


## -parameters




### -param hDrvDevice

A handle to the display device (graphics context).

### -param *pArgs








#### - GetPageableSize [in]

Information used to get pageable size.


#### - hDevice

The handle of a device.


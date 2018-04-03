---
UID: NC:d3d12umddi.PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021
title: PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021
author: windows-driver-content
description: The pfnSetExtendedFeatureCallbacks callback function sets extended feature callbacks.
old-location: display\pfnd3d12ddi_set_extended_feature_callbacks_0021.htm
old-project: display
ms.assetid: 8380C972-D5A0-46D5-B32B-C31D5113BB95
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021, d3d12umddi/pfnSetExtendedFeatureCallbacks, display.pfnd3d12ddi_set_extended_feature_callbacks_0021, pfnSetExtendedFeatureCallbacks, pfnSetExtendedFeatureCallbacks callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
api_name:
-	pfnSetExtendedFeatureCallbacks
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_SET_EXTENDED_FEATURE_CALLBACKS_0021 callback


## -description


The <i>pfnSetExtendedFeatureCallbacks</i> callback function sets extended feature callbacks.


## -parameters




### -param hDevice

The handle of a device.


### -param Table

A value for an implementation of video.


### -param *pTable [in]

A pointer to a table value.


### -param TableSize

The size of the table. 


## -returns



This callback function does not return a value.




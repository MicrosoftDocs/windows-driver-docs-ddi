---
UID: NC:d3d12umddi.PFND3D12DDI_GETKEYBASEDATA_0030
title: PFND3D12DDI_GETKEYBASEDATA_0030
author: windows-driver-content
description: Used to get key base data.
old-location: display\pfnd3d12ddi_getkeybasedata_0030.htm
ms.assetid: D4F893E9-6B7B-4E35-A92F-B31FFD55A2C0
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_GETKEYBASEDATA_0030, PFND3D12DDI_GETKEYBASEDATA_0030 callback, PFND3D12DDI_GETKEYBASEDATA_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_GETKEYBASEDATA_0030, display.pfnd3d12ddi_getkeybasedata_0030
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
-	PFND3D12DDI_GETKEYBASEDATA_0030
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_GETKEYBASEDATA_0030 callback function


## -description


Used to get key base data.


## -parameters




### -param hDrvDevice

The device being processed.


### -param hDrvCryptoSession

The crypto session.


### -param *pKeyInputData [in]

A pointer to key input data.


### -param KeyInputDataSize

The size of the key input data.


### -param *pKeyBaseData [out]

A pointer to key base data.


### -param KeyBaseDataSize

The size of the key base data.


## -returns



Returns STATUS_SUCCESS if completed successfully.




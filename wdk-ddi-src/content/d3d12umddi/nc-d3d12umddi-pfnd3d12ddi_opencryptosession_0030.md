---
UID: NC:d3d12umddi.PFND3D12DDI_OPENCRYPTOSESSION_0030
title: PFND3D12DDI_OPENCRYPTOSESSION_0030
author: windows-driver-content
description: Used to open a crypto session.
old-location: display\pfnd3d12ddi_opencryptosession_0030.htm
ms.assetid: 37A4A739-019E-41E6-B7B8-8F61E915C845
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_OPENCRYPTOSESSION_0030, PFND3D12DDI_OPENCRYPTOSESSION_0030 callback, PFND3D12DDI_OPENCRYPTOSESSION_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_OPENCRYPTOSESSION_0030, display.pfnd3d12ddi_opencryptosession_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	PFND3D12DDI_OPENCRYPTOSESSION_0030
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_OPENCRYPTOSESSION_0030 callback function


## -description


Used to open a crypto session.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to open a crypto session.


### -param hDrvCryptoSession

The crypto session.


## -returns



Returns STATUS_SUCCESS if completed successfully.




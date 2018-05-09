---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
title: PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
author: windows-driver-content
description: Used to create a protected resource session.
old-location: display\pfnd3d12ddi_createprotectedresourcesession_0030.htm
old-project: display
ms.assetid: CE866047-61AD-4F4C-9990-76CE6B7BC4AA
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030, PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030 callback, PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030, display.pfnd3d12ddi_createprotectedresourcesession_0030
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
-	PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3D12DDI_CREATEPROTECTEDRESOURCESESSION_0030 callback function


## -description


Used to create a protected resource session.


## -parameters




### -param hDrvDevice

The hardware device being processed.


### -param *pArgs [in]

The arguments used to create a protected resource session.


### -param hDrvProtectedResourceSession

The protected resource session.


### -param hRtProtectedSession

The protected session.


## -returns



Returns STATUS_SUCCESS if completed successfully.




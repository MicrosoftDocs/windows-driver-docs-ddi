---
UID: NC:d3d12umddi.PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030
title: PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030
author: windows-driver-content
description: Used to set a protected resource session.
old-location: display\pfnd3d12ddi_setprotectedresourcesession_0030_.htm
ms.assetid: 1AF1FA8A-3A7E-4277-B6BE-C41A5C4416B6
ms.date: 5/10/2018
ms.keywords: PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030, PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030  callback, PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030, display.pfnd3d12ddi_setprotectedresourcesession_0030_
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
-	PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_SETPROTECTEDRESOURCESESSION_0030 callback function


## -description


Used to set a protected resource session.


## -parameters




### -param Arg1

*hCommandList*

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

*hProtectedResourceSession*

The protected resource session.


## -returns



This callback function does not return a value.




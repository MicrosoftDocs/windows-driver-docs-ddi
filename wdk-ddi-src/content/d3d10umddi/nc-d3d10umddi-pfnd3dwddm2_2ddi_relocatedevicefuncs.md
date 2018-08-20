---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
title: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS
author: windows-driver-content
description: The pfnRelocateDeviceFuncs callback function specifies the device functions table.
old-location: display\pfnd3dwddm2_2ddi_relocatedevicefuncs.htm
ms.assetid: EAABE65C-3893-4B4C-BB7E-A02F91F869BE
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS, PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback, d3d10umddi/pfnRelocateDeviceFuncs, display.pfnd3dwddm2_2ddi_relocatedevicefuncs, pfnRelocateDeviceFuncs, pfnRelocateDeviceFuncs callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	pfnRelocateDeviceFuncs
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_2DDI_RELOCATEDEVICEFUNCS callback function


## -description


The <i>pfnRelocateDeviceFuncs</i> callback function specifies the device functions table. 


## -parameters




### -param Arg1


### -param *








#### - DeviceFunctions [in]

The device functions table, as a <a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure.


#### - hDevice

The handle of a device.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a>
 

 


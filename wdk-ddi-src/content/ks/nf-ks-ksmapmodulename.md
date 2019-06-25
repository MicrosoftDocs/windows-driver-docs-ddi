---
UID: NF:ks.KsMapModuleName
title: KsMapModuleName function (ks.h)
description: The KsMapModuleName function returns the image name and resource identifier that corresponds to the PhysicalDeviceObject and ModuleName parameters.
old-location: stream\ksmapmodulename.htm
tech.root: stream
ms.assetid: 3223a1bb-ab6c-45d7-9f9a-367a3aa7d465
ms.date: 04/23/2018
ms.keywords: KsMapModuleName, KsMapModuleName function [Streaming Media Devices], ks/KsMapModuleName, ksfunc_76aec7fa-5e31-46d7-b94d-d7bccac7c3cd.xml, stream.ksmapmodulename
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsMapModuleName
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsMapModuleName function


## -description


The <b>KsMapModuleName</b> function returns the image name and resource identifier that corresponds to the <i>PhysicalDeviceObject </i>and<i> ModuleName </i>parameters. 


## -parameters




### -param PhysicalDeviceObject [in]

Pointer to a DEVICE_OBJECT for which to return the requested information.


### -param ModuleName [in]

Pointer to a buffer that contains the module name for which to return the requested information.


### -param ImageName [out]

A caller-allocated buffer that receives the image name for the specified resource.


### -param ResourceId [out]

Pointer to a caller-supplied variable that receives the resource identifier.


### -param ValueType [out]

Pointer to a location into which the function returns the value type of the specified resource.


## -returns



<b>KsMapModuleName</b> returns STATUS_SUCCESS if the requested values are found; otherwise, the routine returns an error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/nf-ks-ksgetimagenameandresourceid">KsGetImageNameAndResourceId</a>
 

 


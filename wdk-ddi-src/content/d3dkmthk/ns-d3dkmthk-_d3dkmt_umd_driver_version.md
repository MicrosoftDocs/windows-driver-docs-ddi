---
UID: NS:d3dkmthk._D3DKMT_UMD_DRIVER_VERSION
title: _D3DKMT_UMD_DRIVER_VERSION
author: windows-driver-content
description: Indicates the version number of the user-mode driver.
old-location: display\d3dkmt_umd_driver_version.htm
old-project: display
ms.assetid: 0661a65d-5129-49f6-9400-70b8c8e8245f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMT_UMD_DRIVER_VERSION, D3DKMT_UMD_DRIVER_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_UMD_DRIVER_VERSION
req.alt-loc: D3dkmthk.h
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
req.typenames: D3DKMT_UMD_DRIVER_VERSION
---

# _D3DKMT_UMD_DRIVER_VERSION structure



## -description
Indicates the version number of the user-mode driver.



## -syntax

````
typedef struct _D3DKMT_UMD_DRIVER_VERSION {
  LARGE_INTEGER DriverVersion;
} D3DKMT_UMD_DRIVER_VERSION;
````


## -struct-fields

### -field DriverVersion

The user-mode driver version.


## -remarks

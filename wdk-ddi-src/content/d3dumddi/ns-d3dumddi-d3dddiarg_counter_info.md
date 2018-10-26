---
UID: NS:d3dumddi.D3DDDIARG_COUNTER_INFO
title: D3DDDIARG_COUNTER_INFO
author: windows-driver-content
description: Describes info to manipulate counters.
old-location: display\d3dddiarg_counter_info.htm
tech.root: display
ms.assetid: FB2B8FBF-908D-4668-8C5B-263903BA1EF5
ms.date: 05/10/2018
ms.keywords: D3DDDIARG_COUNTER_INFO, D3DDDIARG_COUNTER_INFO structure [Display Devices], d3dumddi/D3DDDIARG_COUNTER_INFO, display.d3dddiarg_counter_info
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	HeaderDef
api_location:
-	D3dumddi.h
api_name:
-	D3DDDIARG_COUNTER_INFO
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_COUNTER_INFO
---

# D3DDDIARG_COUNTER_INFO structure


## -description


Describes info to manipulate counters.


## -struct-fields




### -field LastDeviceDependentCounter

A value of type <a href="https://msdn.microsoft.com/f80224c6-9046-4471-b6c6-eb14f02fc51f">D3DDDIQUERYTYPE</a> that identifies the largest device-dependent counter identifier that the device supports. If none are supported, the user-mode display driver must set the value to 0; otherwise, the driver sets the value to greater than or equal to  <b>D3DDDIQUERYTYPE_COUNTER_DEVICE_DEPENDENT</b>.


### -field NumSimultaneousCounters

The number of simultaneously active counters that the driver supports.


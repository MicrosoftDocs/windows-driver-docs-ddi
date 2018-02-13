---
UID: NS:d3dumddi.D3DDDIARG_COUNTER_INFO
title: D3DDDIARG_COUNTER_INFO
author: windows-driver-content
description: Describes info to manipulate counters.
old-location: display\d3dddiarg_counter_info.htm
old-project: display
ms.assetid: FB2B8FBF-908D-4668-8C5B-263903BA1EF5
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3dddiarg_counter_info, D3DDDIARG_COUNTER_INFO, D3DDDIARG_COUNTER_INFO structure [Display Devices], d3dumddi/D3DDDIARG_COUNTER_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3dumddi.h
apiname:
-	D3DDDIARG_COUNTER_INFO
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_COUNTER_INFO
---

# D3DDDIARG_COUNTER_INFO structure


## -description


Describes info to manipulate counters.


## -syntax


````
typedef struct D3DDDIARG_COUNTER_INFO {
  D3DDDIQUERYTYPE LastDeviceDependentCounter;
  UINT            NumSimultaneousCounters;
} D3DDDIARG_COUNTER_INFO;
````


## -struct-fields




### -field LastDeviceDependentCounter

A value of type <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createquery.md">D3DDDIQUERYTYPE</a> that identifies the largest device-dependent counter identifier that the device supports. If none are supported, the user-mode display driver must set the value to 0; otherwise, the driver sets the value to greater than or equal to  <b>D3DDDIQUERYTYPE_COUNTER_DEVICE_DEPENDENT</b>.


### -field NumSimultaneousCounters

The number of simultaneously active counters that the driver supports.


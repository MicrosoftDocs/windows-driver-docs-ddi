---
UID: NS:d3dkmddi._DXGK_CPUHOSTAPERTURE
title: _DXGK_CPUHOSTAPERTURE
author: windows-driver-content
description: DXGK_CPUHOSTAPERTURE describes a memory segment supporting a CPU host aperture.
old-location: display\dxgk_cpuhostaperture.htm
old-project: display
ms.assetid: BBB9D8F6-0EF8-4B34-B79E-8742BB7575D4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_CPUHOSTAPERTURE, DXGK_CPUHOSTAPERTURE structure [Display Devices], d3dkmddi/DXGK_CPUHOSTAPERTURE, _DXGK_CPUHOSTAPERTURE, display.dxgk_cpuhostaperture
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	d3dkmddi.h
apiname: 
-	DXGK_CPUHOSTAPERTURE
product: Windows
targetos: Windows
req.typenames: DXGK_CPUHOSTAPERTURE
---

# _DXGK_CPUHOSTAPERTURE structure


## -description


<b>DXGK_CPUHOSTAPERTURE</b> describes a memory segment supporting a CPU host aperture.


## -syntax


````
typedef struct _DXGK_CPUHOSTAPERTURE {
  UINT64 PhysicalAddress;
  UINT32 SizeInPages;
} DXGK_CPUHOSTAPERTURE;
````


## -struct-fields




### -field PhysicalAddress

The CPU physical address.


### -field SizeInPages

The size d3ddiin CPU host pages.


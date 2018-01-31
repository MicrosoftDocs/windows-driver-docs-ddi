---
UID: NE:d3d12umddi.D3D12DDI_ALLOCATION_INFO_FLAGS_0022
title: D3D12DDI_ALLOCATION_INFO_FLAGS_0022
author: windows-driver-content
description: Contains allocation information flags.
old-location: display\d3d12ddi_allocation_info_flags_0022.htm
old-project: display
ms.assetid: DE3C133C-C1A9-4735-B1C4-9F6E791845A1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_ALLOCATION_INFO_FLAGS_0022 enumeration [Display Devices], display.d3d12ddi_allocation_info_flags_0022, d3d12umddi/D3D12DDI_ALLOCATION_INFO_FLAGS_0022_STEREO, D3D12DDI_ALLOCATION_INFO_FLAGS_0022_NONE, d3d12umddi/D3D12DDI_ALLOCATION_INFO_FLAGS_0022_OVERRIDE_PRIORITY, d3d12umddi/D3D12DDI_ALLOCATION_INFO_FLAGS_0022_PRIMARY, D3D12DDI_ALLOCATION_INFO_FLAGS_0022_STEREO, D3D12DDI_ALLOCATION_INFO_FLAGS_0022_PRIMARY, d3d12umddi/D3D12DDI_ALLOCATION_INFO_FLAGS_0022, d3d12umddi/D3D12DDI_ALLOCATION_INFO_FLAGS_0022_NONE, D3D12DDI_ALLOCATION_INFO_FLAGS_0022_OVERRIDE_PRIORITY, D3D12DDI_ALLOCATION_INFO_FLAGS_0022
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d12umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_ALLOCATION_INFO_FLAGS_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_ALLOCATION_INFO_FLAGS_0022
---

# D3D12DDI_ALLOCATION_INFO_FLAGS_0022 enumeration


## -description


Contains allocation information flags.


## -syntax


````
typedef enum D3D12DDI_ALLOCATION_INFO_FLAGS_0022 { 
  D3D12DDI_ALLOCATION_INFO_FLAGS_0022_NONE               = 0x0,
  D3D12DDI_ALLOCATION_INFO_FLAGS_0022_PRIMARY            = 0x1,
  D3D12DDI_ALLOCATION_INFO_FLAGS_0022_STEREO             = 0x2,
  D3D12DDI_ALLOCATION_INFO_FLAGS_0022_OVERRIDE_PRIORITY  = 0x4
} D3D12DDI_ALLOCATION_INFO_FLAGS_0022;
````


## -enum-fields




#### - D3D12DDI_ALLOCATION_INFO_FLAGS_0022_NONE

No allocation information flag.


#### - D3D12DDI_ALLOCATION_INFO_FLAGS_0022_PRIMARY

A primary value. 


#### - D3D12DDI_ALLOCATION_INFO_FLAGS_0022_STEREO

A stereo value.


#### - D3D12DDI_ALLOCATION_INFO_FLAGS_0022_OVERRIDE_PRIORITY

An override priority. 


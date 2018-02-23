---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
title: D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
author: windows-driver-content
description: Video content protection system support data.
old-location: display\d3d12ddi-video-content-protection-system-support-data-0030.htm
old-project: display
ms.assetid: 82096e3b-574d-44f6-85a9-b560749f6472
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.d3d12ddi-video-content-protection-system-support-data-0030, D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 structure [Display Devices], D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030, d3d12umddi/D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
-	d3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030
---

# D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 structure


## -description


Video content protection system support data.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030 {
  UINT    NodeIndex;
  UINT    ContentProtectionSystemCount;
  GUID *  pContentProtectionSystems;
} D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030, D3D12DDI_VIDEO_CONTENT_PROTECTION_SYSTEM_SUPPORT_DATA_0030;
````


## -struct-fields




### -field NodeIndex

Node index.


### -field ContentProtectionSystemCount

Content protection system count.


### -field pContentProtectionSystems

Content protection systems.


---
UID: NS:d3dkmthk._D3DKMT_DIRECTFLIP_SUPPORT
title: _D3DKMT_DIRECTFLIP_SUPPORT (d3dkmthk.h)
description: Indicates whether the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager (DWM) managed primary allocations.
old-location: display\d3dkmt_directflip_support.htm
ms.assetid: d579d9a3-7db1-47ed-859d-3fed99a4ee9d
ms.date: 05/10/2018
keywords: ["_D3DKMT_DIRECTFLIP_SUPPORT structure"]
ms.keywords: D3DKMT_DIRECTFLIP_SUPPORT, D3DKMT_DIRECTFLIP_SUPPORT structure [Display Devices], _D3DKMT_DIRECTFLIP_SUPPORT, d3dkmthk/D3DKMT_DIRECTFLIP_SUPPORT, display.d3dkmt_directflip_support
f1_keywords:
 - "d3dkmthk/D3DKMT_DIRECTFLIP_SUPPORT"
 - "D3DKMT_DIRECTFLIP_SUPPORT"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmthk.h
api_name:
- D3DKMT_DIRECTFLIP_SUPPORT
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DIRECTFLIP_SUPPORT
---

# _D3DKMT_DIRECTFLIP_SUPPORT structure


## -description


Indicates whether the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the Desktop Window Manager (DWM) managed primary allocations.


## -struct-fields




### -field Supported

If <b>TRUE</b>, the driver supports Direct Flip operations. Otherwise, the driver does not support Direct Flip operations.


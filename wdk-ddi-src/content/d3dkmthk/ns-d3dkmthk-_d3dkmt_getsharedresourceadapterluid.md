---
UID: NS:d3dkmthk._D3DKMT_GETSHAREDRESOURCEADAPTERLUID
title: _D3DKMT_GETSHAREDRESOURCEADAPTERLUID (d3dkmthk.h)
description: Provides information that describes a shared resource and the graphics adapter that the resource was created on.
old-location: display\d3dkmt_getsharedresourceadapterluid.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_GETSHAREDRESOURCEADAPTERLUID structure"]
ms.keywords: D3DKMT_GETSHAREDRESOURCEADAPTERLUID, D3DKMT_GETSHAREDRESOURCEADAPTERLUID structure [Display Devices], _D3DKMT_GETSHAREDRESOURCEADAPTERLUID, d3dkmthk/D3DKMT_GETSHAREDRESOURCEADAPTERLUID, display.d3dkmt_getsharedresourceadapterluid
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_GETSHAREDRESOURCEADAPTERLUID
f1_keywords:
 - _D3DKMT_GETSHAREDRESOURCEADAPTERLUID
 - d3dkmthk/_D3DKMT_GETSHAREDRESOURCEADAPTERLUID
 - D3DKMT_GETSHAREDRESOURCEADAPTERLUID
 - d3dkmthk/D3DKMT_GETSHAREDRESOURCEADAPTERLUID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_GETSHAREDRESOURCEADAPTERLUID
 - D3DKMT_GETSHAREDRESOURCEADAPTERLUID
---

# _D3DKMT_GETSHAREDRESOURCEADAPTERLUID structure


## -description

Provides information that describes a shared resource and the graphics adapter that the resource was created on.

## -struct-fields

### -field hGlobalShare [in]

A handle to the shared resource.

### -field hNtHandle [in]

An NT handle to the process.

### -field AdapterLuid [out]

A LUID that serves as an identifier for the device that the resource indicated by <b>hGlobalShare</b> was created on. <b>LUID</b> is defined in Dxgi.h.


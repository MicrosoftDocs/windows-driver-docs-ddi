---
UID: NS:d3dkmthk._D3DKMT_ENUMADAPTERS
title: _D3DKMT_ENUMADAPTERS (d3dkmthk.h)
description: Supplies information for enumerating all graphics adapters on the system.
old-location: display\d3dkmt_enumadapters.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_ENUMADAPTERS structure"]
ms.keywords: D3DKMT_ENUMADAPTERS, D3DKMT_ENUMADAPTERS structure [Display Devices], _D3DKMT_ENUMADAPTERS, d3dkmthk/D3DKMT_ENUMADAPTERS, display.d3dkmt_enumadapters
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
req.typenames: D3DKMT_ENUMADAPTERS
f1_keywords:
 - _D3DKMT_ENUMADAPTERS
 - d3dkmthk/_D3DKMT_ENUMADAPTERS
 - D3DKMT_ENUMADAPTERS
 - d3dkmthk/D3DKMT_ENUMADAPTERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_ENUMADAPTERS
 - D3DKMT_ENUMADAPTERS
---

# _D3DKMT_ENUMADAPTERS structure


## -description

Supplies information for  enumerating all graphics adapters on the system.

## -struct-fields

### -field NumAdapters

[in] The number of graphics adapters.

### -field Adapters

An array of <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_adapterinfo">D3DKMT_ADAPTERINFO</a> structures that supply configuration information for each adapter. The maximum number of adapters that can be enumerated is 16.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_adapterinfo">D3DKMT_ADAPTERINFO</a>


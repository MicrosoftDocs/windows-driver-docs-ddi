---
UID: NS:d3dkmthk._D3DKMT_OPENADAPTERFROMLUID
title: _D3DKMT_OPENADAPTERFROMLUID (d3dkmthk.h)
description: Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.
old-location: display\d3dkmt_openadapterfromluid.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_OPENADAPTERFROMLUID structure"]
ms.keywords: D3DKMT_OPENADAPTERFROMLUID, D3DKMT_OPENADAPTERFROMLUID structure [Display Devices], _D3DKMT_OPENADAPTERFROMLUID, d3dkmthk/D3DKMT_OPENADAPTERFROMLUID, display.d3dkmt_openadapterfromluid
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
req.typenames: D3DKMT_OPENADAPTERFROMLUID
f1_keywords:
 - _D3DKMT_OPENADAPTERFROMLUID
 - d3dkmthk/_D3DKMT_OPENADAPTERFROMLUID
 - D3DKMT_OPENADAPTERFROMLUID
 - d3dkmthk/D3DKMT_OPENADAPTERFROMLUID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmthk.h
api_name:
 - _D3DKMT_OPENADAPTERFROMLUID
 - D3DKMT_OPENADAPTERFROMLUID
---

# _D3DKMT_OPENADAPTERFROMLUID structure


## -description

Describes the mapping of the given locally unique identifier (LUID) of a device to a graphics adapter handle.

## -struct-fields

### -field AdapterLuid

 [in] A LUID that serves as an identifier for the device. <b>LUID</b> is defined in Dxgi.h.

### -field hAdapter

[out] A handle to the graphics adapter for the device that the <b>AdapterLuid</b> member specifies. The adapter handle is returned from a call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromluid">D3DKMTOpenAdapterFromLuid</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtopenadapterfromluid">D3DKMTOpenAdapterFromLuid</a>


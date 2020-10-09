---
UID: NS:d3dkmthk._D3DKMT_DESTROYDEVICE
title: _D3DKMT_DESTROYDEVICE (d3dkmthk.h)
description: The D3DKMT_DESTROYDEVICE structure contains a handle to the kernel-mode device context to release.
old-location: display\d3dkmt_destroydevice.htm
ms.assetid: f74ea9da-71ba-466a-b102-78d999d38096
ms.date: 05/10/2018
keywords: ["D3DKMT_DESTROYDEVICE structure"]
ms.keywords: D3DKMT_DESTROYDEVICE, D3DKMT_DESTROYDEVICE structure [Display Devices], OpenGL_Structs_dc051065-8102-453f-81cd-aa39ee592926.xml, _D3DKMT_DESTROYDEVICE, d3dkmthk/D3DKMT_DESTROYDEVICE, display.d3dkmt_destroydevice
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DESTROYDEVICE
f1_keywords:
 - _D3DKMT_DESTROYDEVICE
 - d3dkmthk/_D3DKMT_DESTROYDEVICE
 - D3DKMT_DESTROYDEVICE
 - d3dkmthk/D3DKMT_DESTROYDEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - D3DKMT_DESTROYDEVICE
---

# _D3DKMT_DESTROYDEVICE structure


## -description

The D3DKMT_DESTROYDEVICE structure contains a handle to the kernel-mode device context to release.

## -struct-fields

### -field hDevice

[in] A handle to the device context that the Microsoft DirectX graphics kernel subsystem (<i>Dxgkrnl.sys</i>) supplied and that is returned from the call to the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatedevice">D3DKMTCreateDevice</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatedevice">D3DKMTCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroydevice">D3DKMTDestroyDevice</a>
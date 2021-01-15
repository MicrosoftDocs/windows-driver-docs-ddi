---
UID: NS:d3dkmthk._D3DKMT_FLIPQUEUEINFO
title: _D3DKMT_FLIPQUEUEINFO (d3dkmthk.h)
description: The D3DKMT_FLIPQUEUEINFO structure describes information about the graphics adapter's queue of flip operations that the OpenGL installable client driver (ICD) obtains by calling the D3DKMTQueryAdapterInfo function.
old-location: display\d3dkmt_flipqueueinfo.htm
ms.date: 05/10/2018
keywords: ["D3DKMT_FLIPQUEUEINFO structure"]
ms.keywords: D3DKMT_FLIPQUEUEINFO, D3DKMT_FLIPQUEUEINFO structure [Display Devices], OpenGL_Structs_db4a7b98-df53-4e1e-a990-0a2f45d71525.xml, _D3DKMT_FLIPQUEUEINFO, d3dkmthk/D3DKMT_FLIPQUEUEINFO, display.d3dkmt_flipqueueinfo
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
req.typenames: D3DKMT_FLIPQUEUEINFO
f1_keywords:
 - _D3DKMT_FLIPQUEUEINFO
 - d3dkmthk/_D3DKMT_FLIPQUEUEINFO
 - D3DKMT_FLIPQUEUEINFO
 - d3dkmthk/D3DKMT_FLIPQUEUEINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_FLIPQUEUEINFO
 - D3DKMT_FLIPQUEUEINFO
---

# _D3DKMT_FLIPQUEUEINFO structure


## -description

The D3DKMT_FLIPQUEUEINFO structure describes information about the graphics adapter's queue of flip operations that the OpenGL installable client driver (ICD) obtains by calling the <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a> function.

## -struct-fields

### -field MaxHardwareFlipQueueLength

[out] The maximum number of flip operations that can be queued for hardware-flip queuing.

### -field MaxSoftwareFlipQueueLength

[out] The maximum number of flip operations that can be queued for software-flip queuing  on hardware that supports memory mapped I/O (MMIO)-based flips.

### -field FlipFlags

[out] A <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_flipinfoflags">D3DKMT_FLIPINFOFLAGS</a> structure that indicates, in bit-field flags, flipping capabilities.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtqueryadapterinfo">D3DKMTQueryAdapterInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_flipinfoflags">D3DKMT_FLIPINFOFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_queryadapterinfo">D3DKMT_QUERYADAPTERINFO</a>


---
UID: NS:d3dkmthk._D3DKMT_CREATEDEVICEFLAGS
title: _D3DKMT_CREATEDEVICEFLAGS (d3dkmthk.h)
description: The D3DKMT_CREATEDEVICEFLAGS structure identifies the type of device context to be created in a call to the D3DKMTCreateDevice function.
old-location: display\d3dkmt_createdeviceflags.htm
ms.assetid: 90d4ce0a-1f36-4f2e-bdbe-5f80c8dfb92a
ms.date: 05/10/2018
keywords: ["D3DKMT_CREATEDEVICEFLAGS structure"]
ms.keywords: D3DKMT_CREATEDEVICEFLAGS, D3DKMT_CREATEDEVICEFLAGS structure [Display Devices], OpenGL_Structs_7cb495c3-44aa-46cb-8bca-87b66c5d422f.xml, _D3DKMT_CREATEDEVICEFLAGS, d3dkmthk/D3DKMT_CREATEDEVICEFLAGS, display.d3dkmt_createdeviceflags
f1_keywords:
 - "d3dkmthk/D3DKMT_CREATEDEVICEFLAGS"
 - "D3DKMT_CREATEDEVICEFLAGS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_CREATEDEVICEFLAGS
targetos: Windows
tech.root: display
req.typenames: D3DKMT_CREATEDEVICEFLAGS
---

# _D3DKMT_CREATEDEVICEFLAGS structure


## -description


The D3DKMT_CREATEDEVICEFLAGS structure identifies the type of device context to be created in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtcreatedevice">D3DKMTCreateDevice</a> function.


## -struct-fields




### -field LegacyMode

A UINT value that specifies whether the device should imitate several behaviors of legacy devices (that is, from Microsoft DirectDraw through Microsoft Direct3D 9.0 device types).

When legacy mode is enabled, the video memory manager does not allow the device to allocate more video memory than can fit in the combined GPU segment. Primaries are allocated in place in video memory and not preserved across mode switches. 

Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).


### -field RequestVSync

A UINT value that specifies whether the device requires vertical sync to operate. If <b>RequestVSync</b> is set, the operating system will enable vertical sync on the graphics hardware until the display device is released. 

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).


### -field DisableGpuTimeout

Supported in Windows 8 and later versions.A UINT value that specifies whether the device has disabled <a href="https://docs.microsoft.com/windows-hardware/drivers/display/timeout-detection-and-recovery">Timeout Detection and Recovery (TDR)</a>.

Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000004).


### -field Reserved

This member is reserved and should be set to zero. Setting this member is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of a 32-bit value to zeros.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_createdevice">D3DKMT_CREATEDEVICE</a>
 

 


---
UID: NS:d3dkmthk._D3DKMT_CREATEDEVICEFLAGS
title: D3DKMT_CREATEDEVICEFLAGS (d3dkmthk.h)
description: Learn more about the D3DKMT_CREATEDEVICEFLAGS structure.
ms.date: 04/10/2024
keywords: ["D3DKMT_CREATEDEVICEFLAGS structure"]
req.header: d3dkmthk.h
req.construct-type: structure
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3DKMT_CREATEDEVICEFLAGS
f1_keywords:
 - _D3DKMT_CREATEDEVICEFLAGS
 - d3dkmthk/_D3DKMT_CREATEDEVICEFLAGS
 - D3DKMT_CREATEDEVICEFLAGS
 - d3dkmthk/D3DKMT_CREATEDEVICEFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_CREATEDEVICEFLAGS
 - D3DKMT_CREATEDEVICEFLAGS
---

# D3DKMT_CREATEDEVICEFLAGS structure (d3dkmthk.h)



## -description

The **D3DKMT_CREATEDEVICEFLAGS** structure identifies the type of device context to be created in a call to [**D3DKMT_CREATEDEVICE**](ns-d3dkmthk-_d3dkmt_createdevice.md).

## -struct-fields

### -field LegacyMode

A UINT value that specifies whether the device should imitate several behaviors of legacy devices (that is, from Microsoft DirectDraw through Microsoft Direct3D 9.0 device types).

When legacy mode is enabled, the video memory manager does not allow the device to allocate more video memory than can fit in the combined GPU segment. Primaries are allocated in place in video memory and not preserved across mode switches.

### -field RequestVSync

A UINT value that specifies whether the device requires vertical sync to operate. If **RequestVSync** is set, the operating system will enable vertical sync on the graphics hardware until the display device is released.

### -field DisableGpuTimeout

Supported in Windows 8 and later versions.A UINT value that specifies whether the device has disabled [Timeout Detection and Recovery (TDR)](/windows-hardware/drivers/display/timeout-detection-and-recovery).

### -field TestDevice

The device is created by a test. Supported starting in Windows 11, version 22H2 (WDDM 3.1).

### -field Reserved

This member is reserved and should be set to zero.

## -see-also

[**D3DKMT_CREATEDEVICE**](ns-d3dkmthk-_d3dkmt_createdevice.md)

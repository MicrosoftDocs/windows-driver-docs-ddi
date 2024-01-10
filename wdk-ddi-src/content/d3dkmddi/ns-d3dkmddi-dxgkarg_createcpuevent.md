---
UID: NS:d3dkmddi._DXGKARG_CREATECPUEVENT
tech.root: display
title: DXGKARG_CREATECPUEVENT
ms.date: 09/12/2022
targetos: Windows
description: Learn more about the DXGKARG_CREATECPUEVENT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dkmddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 version 21H2 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: DXGKARG_CREATECPUEVENT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_CREATECPUEVENT
 - DXGKARG_CREATECPUEVENT
f1_keywords:
 - _DXGKARG_CREATECPUEVENT
 - d3dkmddi/_DXGKARG_CREATECPUEVENT
 - DXGKARG_CREATECPUEVENT
 - d3dkmddi/DXGKARG_CREATECPUEVENT
dev_langs:
 - c++
helpviewer_keywords:
 - _DXGKARG_CREATECPUEVENT
---

## -description

The **DXGKARG_CREATECPUEVENT** structure is an argument passed to [**DXGKDDI_CREATECPUEVENT**](nc-d3dkmddi-dxgkddi_createcpuevent.md) to create a kernel-mode driver's (KMD's) CPU event object for a corresponding *Dxgkrnl* object.

## -struct-fields

### -field hKmdDevice

[in] The KMD device handle, returned from [**DXGKDDI_CREATEDEVICE**](nc-d3dkmddi-dxgkddi_createdevice.md).

### -field hDxgCpuEvent

[in] *Dxgkrnl*'s CPU event sync object handle. KMD needs to pass this handle to [**DXGKCB_SIGNALEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_signalevent).

### -field Flags

[in] A [**DXGK_CREATECPUEVENTFLAGS**](ns-d3dkmddi-dxgk_createcpueventflags.md) structure specifying creation flags.

### -field hKmdCpuEvent

[out] Handle to the created KMD CPU event object.

## -remarks

See [Signaling a CPU event from KMD](/windows-hardware/drivers/display/signaling-cpu-event-from-kmd) for more information.

## -see-also

[**DXGKCB_SIGNALEVENT**](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_signalevent)

[**DXGKDDI_CREATECPUEVENT**](nc-d3dkmddi-dxgkddi_createcpuevent.md)

[**DXGKDDI_CREATEDEVICE**](nc-d3dkmddi-dxgkddi_createdevice.md)

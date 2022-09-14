---
UID: NS:d3dukmdt._D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
tech.root: display
title: D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
ms.date: 09/12/2022
targetos: Windows
description: Learn more about the D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3dukmdt.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11 (WDDM 3.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
 - D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
f1_keywords:
 - _D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
 - d3dukmdt/_D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
 - D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
 - d3dukmdt/D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
dev_langs:
 - c++
helpviewer_keywords:
 - _D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE
---

## -description

The **D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE** structure defines the kernel-mode driver (KMD) CPU event usage escape when notifying KMD about the intended usage of a KMD CPU event object.

## -struct-fields

### -field EscapeType

[in] A [**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md). Must be set to **D3DDDI_DRIVERESCAPETYPE_CPUEVENTUSAGE**.

### -field hSyncObject

[in] CPU event synchronization object handle, returned from [**D3DKMTCreateSynchronizationObject2**](../d3dkmthk/nf-d3dkmthk-d3dkmtcreatesynchronizationobject2.md).

### -field hKmdCpuEvent

[in] Handle that KMD returned from [**DXGKDDI_CREATECPUEVENT**](../d3dkmddi/nc-d3dkmddi-dxgkddi_createcpuevent.md)

### -field Usage[8]

Driver-defined usage for the synchronization object.

## -remarks

See [Signaling a CPU event from KMD](/windows-hardware/drivers/display/signaling-cpu-event-from-kmd) for more information and sample code.

## -see-also

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DXGKDDI_ESCAPE**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)

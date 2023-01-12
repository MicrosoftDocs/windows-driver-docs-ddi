---
UID: NE:d3dukmdt._D3DDDI_DRIVERESCAPETYPE
title: D3DDDI_DRIVERESCAPETYPE (d3dukmdt.h)
description: Learn more about the D3DDDI_DRIVERESCAPETYPE enumeration.
ms.date: 09/12/2022
keywords: ["D3DDDI_DRIVERESCAPETYPE enumeration"]
ms.keywords: _D3DDDI_DRIVERESCAPETYPE, D3DDDI_DRIVERESCAPETYPE,
req.header: d3dukmdt.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3DDDI_DRIVERESCAPETYPE
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - _D3DDDI_DRIVERESCAPETYPE
 - d3dukmdt/_D3DDDI_DRIVERESCAPETYPE
 - D3DDDI_DRIVERESCAPETYPE
 - d3dukmdt/D3DDDI_DRIVERESCAPETYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - _D3DDDI_DRIVERESCAPETYPE
 - D3DDDI_DRIVERESCAPETYPE
dev_langs:
 - c++
---

# D3DDDI_DRIVERESCAPETYPE enumeration

## -description

**D3DDDI_DRIVERESCAPETYPE** defines the known driver escape types.

## -enum-fields

### -field D3DDDI_DRIVERESCAPETYPE_TRANSLATEALLOCATIONHANDLE:0

Driver escape type to translate allocation handle; used to translate the guest allocation to the corresponding host handle.

### -field D3DDDI_DRIVERESCAPETYPE_TRANSLATERESOURCEHANDLE:1

Driver escape type to translate resource handle; used to translate the resource handle to the corresponding host handle.

### -field D3DDDI_DRIVERESCAPETYPE_CPUEVENTUSAGE:2

Driver escape type for CPU event usage; used to notify the kernel-mode driver (KMD) about the intended use of a KMD CPU event object. Available starting in Windows 11 (WDDM 3.0). See [Signaling a CPU event from KMD](/windows-hardware/drivers/display/signaling-cpu-event-from-kmd) for more information.

### -field D3DDDI_DRIVERESCAPETYPE_MAX

Driver escape type max.

## -see-also

[**D3DDDI_DRIVERESCAPE_CPUEVENTUSAGE**](ns-d3dukmdt-d3dddi_driverescape_cpueventusage.md)

[**D3DDDI_DRIVERESCAPETYPE**](ne-d3dukmdt-_d3dddi_driverescapetype.md)

[**DXGKARG_ESCAPE**](../d3dkmddi/ns-d3dkmddi-_dxgkarg_escape.md)

[**DXGKDDI_ESCAPE**](../d3dkmddi/nc-d3dkmddi-dxgkddi_escape.md)

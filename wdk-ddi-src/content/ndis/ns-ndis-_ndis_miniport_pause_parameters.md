---
UID: NS:ndis._NDIS_MINIPORT_PAUSE_PARAMETERS
title: _NDIS_MINIPORT_PAUSE_PARAMETERS (ndis.h)
description: The NDIS_MINIPORT_PAUSE_PARAMETERS structure defines pause parameters for miniport adapters.
old-location: netvista\ndis_miniport_pause_parameters.htm
tech.root: netvista
ms.date: 10/10/2018
keywords: ["NDIS_MINIPORT_PAUSE_PARAMETERS structure"]
ms.keywords: "*PNDIS_MINIPORT_PAUSE_PARAMETERS, NDIS_MINIPORT_PAUSE_PARAMETERS, NDIS_MINIPORT_PAUSE_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_PAUSE_PARAMETERS, PNDIS_MINIPORT_PAUSE_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_PAUSE_PARAMETERS, miniport_structures_ref_cd7d1bc3-5c65-45c5-8e45-f23619dafff8.xml, ndis/NDIS_MINIPORT_PAUSE_PARAMETERS, ndis/PNDIS_MINIPORT_PAUSE_PARAMETERS, netvista.ndis_miniport_pause_parameters"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.typenames: NDIS_MINIPORT_PAUSE_PARAMETERS, *PNDIS_MINIPORT_PAUSE_PARAMETERS
f1_keywords:
 - _NDIS_MINIPORT_PAUSE_PARAMETERS
 - ndis/_NDIS_MINIPORT_PAUSE_PARAMETERS
 - PNDIS_MINIPORT_PAUSE_PARAMETERS
 - ndis/PNDIS_MINIPORT_PAUSE_PARAMETERS
 - NDIS_MINIPORT_PAUSE_PARAMETERS
 - ndis/NDIS_MINIPORT_PAUSE_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - _NDIS_MINIPORT_PAUSE_PARAMETERS
 - PNDIS_MINIPORT_PAUSE_PARAMETERS
 - NDIS_MINIPORT_PAUSE_PARAMETERS
---

# _NDIS_MINIPORT_PAUSE_PARAMETERS structure


## -description

The NDIS_MINIPORT_PAUSE_PARAMETERS structure defines pause parameters for miniport adapters.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_PAUSE_PARAMETERS structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_MINIPORT_PAUSE_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_PAUSE_PARAMETERS_REVISION_1.

### -field Flags

Reserved.

### -field PauseReason

The value of this member depends on the NDIS version a miniport driver is targeting.

| Miniport driver NDIS version | Value |
| --- | --- | --- |
| Earlier than NDIS 6.40 | Unpredictable values. Miniport drivers should not rely on the value of this member. |
| 6.40 and later | NDIS_PAUSE_MINIPORT_DEVICE_REMOVE under specific conditions, otherwise NDIS_PAUSE_NDIS_INTERNAL. |

For NDIS 6.40 and later miniport drivers running on Windows 10, version 1903 and later, the value of this member might be NDIS_PAUSE_MINIPORT_DEVICE_REMOVE if NDIS guarantees that the miniport adapter instance will never receive a [*MiniportRestart*](nc-ndis-miniport_restart.md) call again. Otherwise, this value is NDIS_PAUSE_NDIS_INTERNAL. If the NDIS_PAUSE_MINIPORT_DEVICE_REMOVE flag is set, miniport drivers can optionally make aggressive performance optimizations in their [*MiniportPause*](nc-ndis-miniport_pause.md) handler that assume that the adapter's datapath will never be restarted. NDIS 6.40 and later drivers will never see NDIS_PAUSE_MINIPORT_DEVICE_REMOVE on versions of Windows earlier than Windows 10, version 1903.

## -remarks

To define miniport adapter pause parameters, NDIS passes a pointer to an
    NDIS_MINIPORT_PAUSE_PARAMETERS structure to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>


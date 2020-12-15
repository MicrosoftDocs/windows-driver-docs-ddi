---
UID: NS:ntddndis._NDIS_WMI_ENUM_ADAPTER
title: _NDIS_WMI_ENUM_ADAPTER (ntddndis.h)
description: The NDIS_WMI_ENUM_ADAPTER structure is returned when NDIS responds to the GUID_NDIS_ENUMERATE_ADAPTERS_EX GUID.
old-location: netvista\ndis_wmi_enum_adapter.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WMI_ENUM_ADAPTER structure"]
ms.keywords: "*PNDIS_WMI_ENUM_ADAPTER, NDIS_WMI_ENUM_ADAPTER, NDIS_WMI_ENUM_ADAPTER structure [Network Drivers Starting with Windows Vista], PNDIS_WMI_ENUM_ADAPTER, PNDIS_WMI_ENUM_ADAPTER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WMI_ENUM_ADAPTER, ndis_wmi_ref_a64c64b4-2108-4b99-937d-098197c5a72c.xml, netvista.ndis_wmi_enum_adapter, ntddndis/NDIS_WMI_ENUM_ADAPTER, ntddndis/PNDIS_WMI_ENUM_ADAPTER"
req.header: ntddndis.h
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
req.typenames: NDIS_WMI_ENUM_ADAPTER, *PNDIS_WMI_ENUM_ADAPTER
f1_keywords:
 - _NDIS_WMI_ENUM_ADAPTER
 - ntddndis/_NDIS_WMI_ENUM_ADAPTER
 - PNDIS_WMI_ENUM_ADAPTER
 - ntddndis/PNDIS_WMI_ENUM_ADAPTER
 - NDIS_WMI_ENUM_ADAPTER
 - ntddndis/NDIS_WMI_ENUM_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_WMI_ENUM_ADAPTER
---

# _NDIS_WMI_ENUM_ADAPTER structure


## -description

The NDIS_WMI_ENUM_ADAPTER structure is returned when NDIS responds to the 
  <a href="/windows-hardware/drivers/network/guid-ndis-enumerate-adapters-ex">
  GUID_NDIS_ENUMERATE_ADAPTERS_EX</a> GUID.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_ENUM_ADAPTER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_ENUM_ADAPTER, the 
     <b>Revision</b> member to NDIS_WMI_ENUM_ADAPTER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_ENUM_ADAPTER).

### -field IfIndex

The NDIS interface index of the NDIS miniport adapter interface that is associated with the
     GUID.

### -field NetLuid

The NDIS network interface name of the miniport adapter.

### -field DeviceNameLength

The length, in bytes, of the device name of the NDIS miniport adapter interface that is associated
     with the GUID.

### -field DeviceName

The device name of the NDIS miniport adapter interface that is associated with the GUID. The
     device name is a null-terminated wide character string.

## -remarks

NDIS returns the NDIS_WMI_ENUM_ADAPTER structure when it enumerates miniport adapters for WMI clients.
    For more information about enumerating miniport adapters for WMI clients, see 
    <a href="/windows-hardware/drivers/network/guid-ndis-enumerate-adapters-ex">
    GUID_NDIS_ENUMERATE_ADAPTERS_EX</a>.

## -see-also

<a href="/windows-hardware/drivers/network/guid-ndis-enumerate-adapters-ex">GUID_NDIS_ENUMERATE_ADAPTERS_EX</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>

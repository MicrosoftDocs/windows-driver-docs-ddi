---
UID: NS:ntddndis._NDIS_WMI_METHOD_HEADER
title: _NDIS_WMI_METHOD_HEADER (ntddndis.h)
description: The NDIS_WMI_METHOD_HEADER structure provides information about a GUID method request from WMI clients.
old-location: netvista\ndis_wmi_method_header.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_WMI_METHOD_HEADER structure"]
ms.keywords: "*PNDIS_WMI_METHOD_HEADER, NDIS_WMI_METHOD_HEADER, NDIS_WMI_METHOD_HEADER structure [Network Drivers Starting with Windows Vista], PNDIS_WMI_METHOD_HEADER, PNDIS_WMI_METHOD_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WMI_METHOD_HEADER, ndis_wmi_ref_fa232798-c72c-4823-806a-c8b7cf28001d.xml, netvista.ndis_wmi_method_header, ntddndis/NDIS_WMI_METHOD_HEADER, ntddndis/PNDIS_WMI_METHOD_HEADER"
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
req.typenames: NDIS_WMI_METHOD_HEADER, *PNDIS_WMI_METHOD_HEADER
f1_keywords:
 - _NDIS_WMI_METHOD_HEADER
 - ntddndis/_NDIS_WMI_METHOD_HEADER
 - PNDIS_WMI_METHOD_HEADER
 - ntddndis/PNDIS_WMI_METHOD_HEADER
 - NDIS_WMI_METHOD_HEADER
 - ntddndis/NDIS_WMI_METHOD_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_WMI_METHOD_HEADER
---

# _NDIS_WMI_METHOD_HEADER structure


## -description

The NDIS_WMI_METHOD_HEADER structure provides information about a GUID method request from WMI
  clients.

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_METHOD_HEADER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_METHOD, the 
     <b>Revision</b> member to NDIS_GUID_HEADER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_METHOD_HEADER).

### -field PortNumber

The miniport adapter port, if any. If the GUID is not specific to a port, 
     <b>PortNumber</b> is zero. WMI clients can use the 
     <a href="/windows-hardware/drivers/network/guid-ndis-gen-enumerate-ports">
     GUID_NDIS_GEN_ENUMERATE_PORTS</a> GUID to obtain list of the ports that are associated with a miniport
     adapter.

### -field NetLuid

The NDIS network interface name of the miniport adapter. WMI clients can use the 
     <a href="/windows-hardware/drivers/network/guid-ndis-enumerate-adapters-ex">
     GUID_NDIS_ENUMERATE_ADAPTERS_EX</a> GUID to find a device name and the associated 
     <b>NetLuid</b> value.

### -field RequestId

An identifier for the request. If a miniport driver must complete a request immediately and it
     completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the miniport driver uses this 
     <b>RequestId</b> value to set the 
     <b>RequestId</b> member of the associated 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure. 
     

NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member.

For more information about this member, see 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>.

### -field Timeout

A time-out, in seconds, for the request. NDIS can reset the driver or cancel the request if the
      time-out expires before the driver completes the request.

For more information about this member, see 
      <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>.

### -field Padding

This member is reserved.

## -remarks

NDIS translates WMI GUID method requests to NDIS OID requests.

WMI method GUID requests that are specific to NDIS 6.0 and later versions include an
    NDIS_WMI_METHOD_HEADER structure that is followed by the GUID-specific data, if any. The WMI output
    buffer contains GUID-specific data, if any, when the request succeeds and completes.

## -see-also

<a href="/windows-hardware/drivers/network/guid-ndis-enumerate-adapters-ex">GUID_NDIS_ENUMERATE_ADAPTERS_EX</a>



<a href="/windows-hardware/drivers/network/guid-ndis-gen-enumerate-ports">GUID_NDIS_GEN_ENUMERATE_PORTS</a>



<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>

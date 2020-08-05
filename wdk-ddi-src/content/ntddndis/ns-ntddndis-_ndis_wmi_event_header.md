---
UID: NS:ntddndis._NDIS_WMI_EVENT_HEADER
title: _NDIS_WMI_EVENT_HEADER (ntddndis.h)
description: The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.
old-location: netvista\ndis_wmi_event_header.htm
tech.root: netvista
ms.assetid: b9e2c393-cf77-4193-ba59-b8eb914ef1e6
ms.date: 05/02/2018
keywords: ["NDIS_WMI_EVENT_HEADER structure"]
ms.keywords: "*PNDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER structure [Network Drivers Starting with Windows Vista], PNDIS_WMI_EVENT_HEADER, PNDIS_WMI_EVENT_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WMI_EVENT_HEADER, ndis_wmi_ref_ebe1bff7-7e6d-47e7-b79c-3e53a733ac54.xml, netvista.ndis_wmi_event_header, ntddndis/NDIS_WMI_EVENT_HEADER, ntddndis/PNDIS_WMI_EVENT_HEADER"
f1_keywords:
 - "ntddndis/NDIS_WMI_EVENT_HEADER"
 - "NDIS_WMI_EVENT_HEADER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddndis.h
api_name:
- NDIS_WMI_EVENT_HEADER
targetos: Windows
req.typenames: NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER
---

# _NDIS_WMI_EVENT_HEADER structure


## -description


The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_EVENT_HEADER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_EVENT, the 
     <b>Revision</b> member to NDIS_WMI_EVENT_HEADER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_EVENT_HEADER).


### -field IfIndex

The NDIS interface index of the NDIS miniport adapter interface that is associated with the
     GUID.


### -field NetLuid

The NDIS network interface name of the miniport adapter.


### -field RequestId

An identifier for the request. If a miniport driver must complete a request immediately and it
     completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the miniport driver uses this 
     <b>RequestId</b> value to set the 
     <b>RequestId</b> member of the associated 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure. 
     

NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member.

For more information about this member, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>.


### -field PortNumber

The miniport adapter port, if any. If the GUID is not specific to a port, 
     <b>PortNumber</b> is zero.


### -field DeviceNameLength

The length, in bytes, of the device name.


### -field DeviceNameOffset

The offset, in bytes, to the beginning of the device name from the beginning of the
     NDIS_WMI_EVENT_HEADER structure.


### -field Padding

This member is reserved.


## -remarks



NDIS translates NDIS status indications to WMI GUID event indications.

WMI GUID event indications that are specific to NDIS 6.0 and later versions include an
    NDIS_WMI_EVENT_HEADER structure that is followed by the GUID-specific data, if any.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>
 

 


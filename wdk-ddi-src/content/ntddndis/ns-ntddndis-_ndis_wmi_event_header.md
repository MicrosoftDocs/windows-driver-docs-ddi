---
UID: NS:ntddndis._NDIS_WMI_EVENT_HEADER
title: "_NDIS_WMI_EVENT_HEADER"
author: windows-driver-content
description: The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.
old-location: netvista\ndis_wmi_event_header.htm
old-project: netvista
ms.assetid: b9e2c393-cf77-4193-ba59-b8eb914ef1e6
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER structure [Network Drivers Starting with Windows Vista], PNDIS_WMI_EVENT_HEADER, PNDIS_WMI_EVENT_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WMI_EVENT_HEADER, ndis_wmi_ref_ebe1bff7-7e6d-47e7-b79c-3e53a733ac54.xml, netvista.ndis_wmi_event_header, ntddndis/NDIS_WMI_EVENT_HEADER, ntddndis/PNDIS_WMI_EVENT_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddndis.h
apiname:
-	NDIS_WMI_EVENT_HEADER
product: Windows
targetos: Windows
req.typenames: NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER
---

# _NDIS_WMI_EVENT_HEADER structure


## -description


The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.


## -syntax


````
typedef struct _NDIS_WMI_EVENT_HEADER {
  NDIS_OBJECT_HEADER Header;
  NET_IFINDEX        IfIndex;
  NET_LUID           NetLuid;
  ULONG64            RequestId;
  NDIS_PORT_NUMBER   PortNumber;
  ULONG              DeviceNameLength;
  ULONG              DeviceNameOffset;
  UCHAR              Padding[4];
} NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for this
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
     <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure. 
     

NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member.

For more information about this member, see 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>.


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

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WMI_EVENT_HEADER structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


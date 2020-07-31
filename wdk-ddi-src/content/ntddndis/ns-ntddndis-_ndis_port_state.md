---
UID: NS:ntddndis._NDIS_PORT_STATE
title: _NDIS_PORT_STATE (ntddndis.h)
description: The NDIS_PORT_STATE structure specifies the port state information for an NDIS port.
old-location: netvista\ndis_port_state.htm
tech.root: netvista
ms.assetid: 57d76d1e-4276-4dbd-b651-2bba6de898b2
ms.date: 05/02/2018
keywords: ["_NDIS_PORT_STATE structure"]
ms.keywords: "*PNDIS_PORT_STATE, NDIS_PORT_STATE, NDIS_PORT_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_PORT_STATE, PNDIS_PORT_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT_STATE, ndis_ports_ref_dbfd8cd5-9c0c-4ea9-8329-d9fbf15b14df.xml, netvista.ndis_port_state, ntddndis/NDIS_PORT_STATE, ntddndis/PNDIS_PORT_STATE"
f1_keywords:
 - "ntddndis/NDIS_PORT_STATE"
 - "NDIS_PORT_STATE"
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
- NDIS_PORT_STATE
targetos: Windows
req.typenames: NDIS_PORT_STATE, *PNDIS_PORT_STATE
---

# _NDIS_PORT_STATE structure


## -description


The NDIS_PORT_STATE structure specifies the port state information for an NDIS port.


## -struct-fields




### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PORT_STATE structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_ DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_STATE_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_STATE_REVISION_1.


### -field MediaConnectState

The media connection state of the port. This state is the same information that the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a> OID returns.


### -field XmitLinkSpeed

The transmit link speed of the port, in bits per second. A value of -1 in this member indicates
     that the transmit link speed is unknown.


### -field RcvLinkSpeed

The receive link speed of the port, in bits per second. A value of -1 in this member indicates
     that the receive link speed is unknown.


### -field Direction

A 
     <a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_direction_type">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.


### -field SendControlState

The current control state of the port for send operations. This member must contain one of the
     following values:
     





#### NdisPortControlStateUnknown

The port's control state for send operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for send operations. That is, the port requires
       authorization.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for send operations. That is, the port does not require
       authorization.


### -field RcvControlState

The current control state of the port for receive operations. This member must contain one of the
     following values:
     





#### NdisPortControlStateUnknown

The port's control state for receive operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for receive operations. That is, the port requires
       authorization.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for receive operations. That is, the port does not require
       authorization.


### -field SendAuthorizationState

The current authorization state of the port for send operations. Ignore this member if the 
     <b>SendControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

<b>SendAuthorizationState</b> must contain one of the following values:





#### NdisPortAuthorizationUnknown

The port's authorization state for send operations is unknown.



#### NdisPortAuthorized

The port is authorized for send operations.



#### NdisPortUnauthorized

The port is not authorized for send operations.



#### NdisPortReauthorizing

The port is re-authorizing for send operations.


### -field RcvAuthorizationState

The current authorization state of the port for receive operations. Ignore this member if the 
     <b>RcvControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

<b>RcvAuthorizationState</b> must contain one of the following values:





#### NdisPortAuthorizationUnknown

The port's authorization state for receive operations is unknown.



#### NdisPortAuthorized

The port is authorized for receive operations.



#### NdisPortUnauthorized

The port is not authorized for receive operations.



#### NdisPortReauthorizing

The port is re-authorizing for receive operations.


### -field Flags

Reserved for NDIS.


## -remarks



The NDIS_PORT_STATE structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-port-state">NDIS_STATUS_PORT_STATE</a> status
    indication to indicate a change in the state of a port and is used in response to an 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-state">OID_GEN_PORT_STATE</a> OID query.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-port-state">NDIS_STATUS_PORT_STATE</a>



<a href="https://docs.microsoft.com/windows/win32/api/ifdef/ne-ifdef-net_if_direction_type">NET_IF_DIRECTION_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-state">OID_GEN_PORT_STATE</a>
 

 


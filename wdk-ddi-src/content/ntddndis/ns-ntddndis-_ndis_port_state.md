---
UID: NS:ntddndis._NDIS_PORT_STATE
title: "_NDIS_PORT_STATE"
author: windows-driver-content
description: The NDIS_PORT_STATE structure specifies the port state information for an NDIS port.
old-location: netvista\ndis_port_state.htm
old-project: netvista
ms.assetid: 57d76d1e-4276-4dbd-b651-2bba6de898b2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_PORT_STATE, NDIS_PORT_STATE, NDIS_PORT_STATE structure [Network Drivers Starting with Windows Vista], PNDIS_PORT_STATE, PNDIS_PORT_STATE structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT_STATE, ndis_ports_ref_dbfd8cd5-9c0c-4ea9-8329-d9fbf15b14df.xml, netvista.ndis_port_state, ntddndis/NDIS_PORT_STATE, ntddndis/PNDIS_PORT_STATE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_PORT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_PORT_STATE, *PNDIS_PORT_STATE
---

# _NDIS_PORT_STATE structure


## -description


The NDIS_PORT_STATE structure specifies the port state information for an NDIS port.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PORT_STATE structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_ DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_STATE_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_STATE_REVISION_1.


### -field MediaConnectState

The media connection state of the port. This state is the same information that the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a> OID returns.


### -field XmitLinkSpeed

The transmit link speed of the port, in bits per second. A value of -1 in this member indicates
     that the transmit link speed is unknown.


### -field RcvLinkSpeed

The receive link speed of the port, in bits per second. A value of -1 in this member indicates
     that the receive link speed is unknown.


### -field Direction

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a> NDIS network
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
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff567415">NDIS_STATUS_PORT_STATE</a> status
    indication to indicate a change in the state of a port and is used in response to an 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569624">OID_GEN_PORT_STATE</a> OID query.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567415">NDIS_STATUS_PORT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569624">OID_GEN_PORT_STATE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT_STATE structure%20 RELEASE:%20(3/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


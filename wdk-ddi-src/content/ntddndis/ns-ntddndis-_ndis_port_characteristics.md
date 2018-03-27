---
UID: NS:ntddndis._NDIS_PORT_CHARACTERISTICS
title: "_NDIS_PORT_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_PORT_CHARACTERISTICS structure specifies the characteristics of an NDIS port. For more information about NDIS ports, see NDIS Ports.
old-location: netvista\ndis_port_characteristics.htm
old-project: netvista
ms.assetid: fd602dd6-c216-413a-a4da-292739774937
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_PORT_CHARACTERISTICS, NDIS_PORT_CHARACTERISTICS, NDIS_PORT_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PORT_CHARACTERISTICS, PNDIS_PORT_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT_CHARACTERISTICS, ndis_ports_ref_2b3ef68d-2ed2-4a06-ab0c-3df59bf7d7a5.xml, netvista.ndis_port_characteristics, ntddndis/NDIS_PORT_CHARACTERISTICS, ntddndis/PNDIS_PORT_CHARACTERISTICS"
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
-	NDIS_PORT_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_PORT_CHARACTERISTICS, *PNDIS_PORT_CHARACTERISTICS
---

# _NDIS_PORT_CHARACTERISTICS structure


## -description


The <b>NDIS_PORT_CHARACTERISTICS</b> structure specifies the characteristics of an NDIS port. For more information about NDIS ports, see <a href="https://msdn.microsoft.com/e65f4af5-c527-4d6d-a38c-56da006b1ef7">NDIS Ports</a>.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_PORT_CHARACTERISTICS</b> structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_CHARACTERISTICS_REVISION_1.


### -field PortNumber

The number of the NDIS port that is associated with this <b>NDIS_PORT_CHARACTERISTICS</b> structure. The 
     <b>PortNumber</b> value is an NDIS_PORT_NUMBER value, which has a ULONG data type and is valid from zero
     through 0xffffff, where zero is reserved for the default port.


### -field Flags

A bitwise OR combination of the port characteristics flags, or zero if no flags are set. There is
     currently one flag.
     

If the NDIS_PORT_CHAR_USE_DEFAULT_AUTH_SETTINGS flag is set, NDIS ignores authentication state
     settings and uses the default authentication state instead. A miniport driver can use this flag to
     request that NDIS use the default authentication state settings for the ports that it allocates and
     activates. If the miniport driver controls the default port, when the miniport driver activates the
     default port, the driver can set NDIS_PORT_CHAR_USE_DEFAULT_AUTH_SETTINGS to activate the default port
     with the default authentication state settings.


### -field Type

The type of NDIS port. For more information, see <a href="https://msdn.microsoft.com/a77ceb1b-d4b9-4a42-aa5b-685295722fa3">Types of NDIS Ports</a>. This type can be one of the following values:
     





#### NdisPortTypeUndefined

The default port type.



#### NdisPortTypeBridge

Reserved for system use.



#### NdisPortTypeRasConnection

A Remote Access Service (RAS) connection.



#### NdisPortType8021xSupplicant

A remote wireless station that is associated with an access point on this host computer.



#### NdisPortTypeNdisImPlatform

Reserved for system use.

<div class="alert"><b>Note</b>  This value is supported only in NDIS 6.30 and later.</div>
<div> </div>

### -field MediaConnectState

The media connection state of the port. This state is the same information that the 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">
     OID_GEN_MEDIA_CONNECT_STATUS_EX</a> OID returns.


### -field XmitLinkSpeed

The transmit link speed of the port in bits per second. A value of -1 in this member indicates
     that the transmit link speed is unknown.


### -field RcvLinkSpeed

The receive link speed of the port, in bits per second. A value of -1 in this member indicates
     that the receive link speed is unknown.


### -field Direction

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a> NDIS network
     interface direction type.


### -field SendControlState

The control state of the port for send operations. This member must contain one of the following
     values:
     





#### NdisPortControlStateUnknown

The port's control state for send operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for send operations. That is, the port requires
       authorization.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for send operations. That is, the port does not require
       authorization.


### -field RcvControlState

The control state of the port for receive operations. This member must contain one of the
     following values:
     





#### NdisPortControlStateUnknown

The port's control state for receive operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for receive operations (that is, the port requires
       authorization), and the value in the 
       <b>SendAuthorizationState</b> member determines the authentication state.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for receive operations. Therefore, authentication does not
       apply to this port.


### -field SendAuthorizationState

The authorization state of the port for send operations. Ignore this member if the 
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

The authorization state of the port for receive operations. Ignore this member if the 
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


## -remarks



The <b>NDIS_PORT_CHARACTERISTICS</b> structure specifies the characteristics of an NDIS port. This structure
    appears in a list of port characteristics that are provided in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566786">NDIS_PORT_ARRAY</a> structure that is used with
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a> OID.

To allocate an NDIS port, a driver initializes an <b>NDIS_PORT_CHARACTERISTICS</b> structure and passes it to
    the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a> function. When 
    <b>NdisMAllocatePort</b> successfully returns, NDIS sets the 
    <b>PortNumber</b> member of <b>NDIS_PORT_CHARACTERISTICS</b> to the port number that NDIS assigned to the
    port.

NDIS uses a linked list of ports in port activation Plug and Play (PnP) events. NDIS uses the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff566769">NDIS_PORT</a> structure to create a linked list of
    ports, and each <b>NDIS_PORT</b> structure contains an <b>NDIS_PORT_CHARACTERISTICS</b> structure.




## -see-also




<a href="https://msdn.microsoft.com/e65f4af5-c527-4d6d-a38c-56da006b1ef7">NDIS Ports</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566769">NDIS_PORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566786">NDIS_PORT_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562779">NdisMAllocatePort</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569583">OID_GEN_ENUMERATE_PORTS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="https://msdn.microsoft.com/a77ceb1b-d4b9-4a42-aa5b-685295722fa3">Types of NDIS Ports</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT_CHARACTERISTICS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


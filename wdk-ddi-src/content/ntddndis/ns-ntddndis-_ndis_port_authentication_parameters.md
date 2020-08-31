---
UID: NS:ntddndis._NDIS_PORT_AUTHENTICATION_PARAMETERS
title: _NDIS_PORT_AUTHENTICATION_PARAMETERS (ntddndis.h)
description: The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS port.
old-location: netvista\ndis_port_authentication_parameters.htm
tech.root: netvista
ms.assetid: 7c411d9e-1064-4278-9870-0546891d4743
ms.date: 05/02/2018
keywords: ["NDIS_PORT_AUTHENTICATION_PARAMETERS structure"]
ms.keywords: "*PNDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_PORT_AUTHENTICATION_PARAMETERS, PNDIS_PORT_AUTHENTICATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PORT_AUTHENTICATION_PARAMETERS, ndis_ports_ref_f78165f6-8166-4889-98e8-6c9f99fe0a0e.xml, netvista.ndis_port_authentication_parameters, ntddndis/NDIS_PORT_AUTHENTICATION_PARAMETERS, ntddndis/PNDIS_PORT_AUTHENTICATION_PARAMETERS"
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
req.typenames: NDIS_PORT_AUTHENTICATION_PARAMETERS, *PNDIS_PORT_AUTHENTICATION_PARAMETERS
f1_keywords:
 - _NDIS_PORT_AUTHENTICATION_PARAMETERS
 - ntddndis/_NDIS_PORT_AUTHENTICATION_PARAMETERS
 - PNDIS_PORT_AUTHENTICATION_PARAMETERS
 - ntddndis/PNDIS_PORT_AUTHENTICATION_PARAMETERS
 - NDIS_PORT_AUTHENTICATION_PARAMETERS
 - ntddndis/NDIS_PORT_AUTHENTICATION_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_PORT_AUTHENTICATION_PARAMETERS
---

# _NDIS_PORT_AUTHENTICATION_PARAMETERS structure


## -description

The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS
  port.

## -struct-fields

### -field Header

The 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PORT_AUTHENTICATION_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_AUTHENTICATION_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_AUTHENTICATION_PARAMETERS_REVISION_1.

### -field SendControlState

The control state of the port that the miniport adapter should use for send operations. This
     member must contain one of the following values:
     





#### NdisPortControlStateUnknown

The port's control state for send operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for send operations. That is, the port requires
       authorization.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for send operations. That is, the port does not require
       authorization.

### -field RcvControlState

The control state of the port that the miniport adapter should use for receive operations. This
     member must contain one of the following values:
     





#### NdisPortControlStateUnknown

The port's control state for receive operations is unknown.



#### NdisPortControlStateControlled

The port is in a controlled state for receive operations. That is, the port requires
       authorization.



#### NdisPortControlStateUncontrolled

The port is in an uncontrolled state for receive operations. That is, the port does not require
       authorization.

### -field SendAuthorizationState

The authorization state of the port that the miniport adapter should use for send operations.
     Ignore this member if the 
     <b>SendControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:





#### NdisPortAuthorizationUnknown

The port's authorization state for send operations is unknown.



#### NdisPortAuthorized

The port is authorized for send operations.



#### NdisPortUnauthorized

The port is not authorized for send operations.



#### NdisPortReauthorizing

The port is re-authorizing for send operations.

### -field RcvAuthorizationState

The authorization state of the port that the miniport adapter should use for receive operations.
     Ignore this member if the 
     <b>RcvControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:





#### NdisPortAuthorizationUnknown

The port's authorization state for receive operations is unknown.



#### NdisPortAuthorized

The port is authorized for receive operations.



#### NdisPortUnauthorized

The port is not authorized for receive operations.



#### NdisPortReauthorizing

The port is re-authorizing for receive operations.

## -remarks

The NDIS_PORT_AUTHENTICATION_PARAMETERS structure is used in 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
    OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a> OID requests to specify the current authentication state of
    an NDIS port.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>


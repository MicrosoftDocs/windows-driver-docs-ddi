---
UID: NS:ntddndis._NDIS_PORT_AUTHENTICATION_PARAMETERS
title: _NDIS_PORT_AUTHENTICATION_PARAMETERS
author: windows-driver-content
description: The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS port.
old-location: netvista\ndis_port_authentication_parameters.htm
old-project: netvista
ms.assetid: 7c411d9e-1064-4278-9870-0546891d4743
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/PNDIS_PORT_AUTHENTICATION_PARAMETERS, _NDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS, ndis_ports_ref_f78165f6-8166-4889-98e8-6c9f99fe0a0e.xml, PNDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS structure [Network Drivers Starting with Windows Vista], *PNDIS_PORT_AUTHENTICATION_PARAMETERS, netvista.ndis_port_authentication_parameters, ntddndis/NDIS_PORT_AUTHENTICATION_PARAMETERS, PNDIS_PORT_AUTHENTICATION_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista]
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
-	NDIS_PORT_AUTHENTICATION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: *PNDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS
---

# _NDIS_PORT_AUTHENTICATION_PARAMETERS structure


## -description


The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS
  port.


## -syntax


````
typedef struct _NDIS_PORT_AUTHENTICATION_PARAMETERS {
  NDIS_OBJECT_HEADER            Header;
  NDIS_PORT_CONTROLL_STATE      SendControlState;
  NDIS_PORT_CONTROLL_STATE      RcvControlState;
  NDIS_PORT_AUTHORIZATION_STATE SendAuthorizationState;
  NDIS_PORT_AUTHORIZATION_STATE RcvAuthorizationState;
} NDIS_PORT_AUTHENTICATION_PARAMETERS, *PNDIS_PORT_AUTHENTICATION_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_PORT_AUTHENTICATION_PARAMETERS structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_PORT_AUTHENTICATION_PARAMETERS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_PORT_AUTHENTICATION_PARAMETERS_REVISION_1.


### -field SendControlState

The control state of the port that the miniport adapter should use for send operations. This
     member must contain one of the following values:
     




### -field RcvControlState

The control state of the port that the miniport adapter should use for receive operations. This
     member must contain one of the following values:
     




### -field SendAuthorizationState

The authorization state of the port that the miniport adapter should use for send operations.
     Ignore this member if the 
     <b>SendControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:




### -field RcvAuthorizationState

The authorization state of the port that the miniport adapter should use for receive operations.
     Ignore this member if the 
     <b>RcvControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:




##### - RcvControlState.NdisPortControlStateUncontrolled

The port is in an uncontrolled state for receive operations. That is, the port does not require
       authorization.


##### - SendControlState.NdisPortControlStateControlled

The port is in a controlled state for send operations. That is, the port requires
       authorization.


##### - SendAuthorizationState.NdisPortReauthorizing

The port is re-authorizing for send operations.


##### - SendAuthorizationState.NdisPortAuthorizationUnknown

The port's authorization state for send operations is unknown.


##### - RcvAuthorizationState.NdisPortReauthorizing

The port is re-authorizing for receive operations.


##### - RcvControlState.NdisPortControlStateUnknown

The port's control state for receive operations is unknown.


##### - RcvControlState.NdisPortControlStateControlled

The port is in a controlled state for receive operations. That is, the port requires
       authorization.


##### - SendAuthorizationState.NdisPortAuthorized

The port is authorized for send operations.


##### - SendControlState.NdisPortControlStateUnknown

The port's control state for send operations is unknown.


##### - RcvAuthorizationState.NdisPortAuthorizationUnknown

The port's authorization state for receive operations is unknown.


##### - RcvAuthorizationState.NdisPortAuthorized

The port is authorized for receive operations.


##### - SendAuthorizationState.NdisPortUnauthorized

The port is not authorized for send operations.


##### - SendControlState.NdisPortControlStateUncontrolled

The port is in an uncontrolled state for send operations. That is, the port does not require
       authorization.


##### - RcvAuthorizationState.NdisPortUnauthorized

The port is not authorized for receive operations.


## -remarks


The NDIS_PORT_AUTHENTICATION_PARAMETERS structure is used in 
    <mshelp:link keywords="netvista.oid_gen_port_authentication_parameters" tabindex="0">
    OID_GEN_PORT_AUTHENTICATION_PARAMETERS</mshelp:link> OID requests to specify the current authentication state of
    an NDIS port.



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<mshelp:link keywords="netvista.oid_gen_port_authentication_parameters" tabindex="0">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT_AUTHENTICATION_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


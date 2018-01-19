---
UID: NS:ntddndis._NDIS_PORT_AUTHENTICATION_PARAMETERS
title: _NDIS_PORT_AUTHENTICATION_PARAMETERS
author: windows-driver-content
description: The NDIS_PORT_AUTHENTICATION_PARAMETERS structure specifies the state parameters for an NDIS port.
old-location: netvista\ndis_port_authentication_parameters.htm
old-project: netvista
ms.assetid: 7c411d9e-1064-4278-9870-0546891d4743
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_PORT_AUTHENTICATION_PARAMETERS, *PNDIS_PORT_AUTHENTICATION_PARAMETERS, NDIS_PORT_AUTHENTICATION_PARAMETERS
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
req.alt-api: NDIS_PORT_AUTHENTICATION_PARAMETERS
req.alt-loc: ntddndis.h
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
     




### -field NdisPortControlStateUnknown

The port's control state for send operations is unknown.


### -field NdisPortControlStateControlled

The port is in a controlled state for send operations. That is, the port requires
       authorization.


### -field NdisPortControlStateUncontrolled

The port is in an uncontrolled state for send operations. That is, the port does not require
       authorization.

</dd>
</dl>

### -field RcvControlState

The control state of the port that the miniport adapter should use for receive operations. This
     member must contain one of the following values:
     




### -field NdisPortControlStateUnknown

The port's control state for receive operations is unknown.


### -field NdisPortControlStateControlled

The port is in a controlled state for receive operations. That is, the port requires
       authorization.


### -field NdisPortControlStateUncontrolled

The port is in an uncontrolled state for receive operations. That is, the port does not require
       authorization.

</dd>
</dl>

### -field SendAuthorizationState

The authorization state of the port that the miniport adapter should use for send operations.
     Ignore this member if the 
     <b>SendControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:




### -field NdisPortAuthorizationUnknown

The port's authorization state for send operations is unknown.


### -field NdisPortAuthorized

The port is authorized for send operations.


### -field NdisPortUnauthorized

The port is not authorized for send operations.


### -field NdisPortReauthorizing

The port is re-authorizing for send operations.

</dd>
</dl>

### -field RcvAuthorizationState

The authorization state of the port that the miniport adapter should use for receive operations.
     Ignore this member if the 
     <b>RcvControlState</b> member is set to 
     <b>NdisPortControlStateUncontrolled</b>.
     

This member must contain one of the following values:




### -field NdisPortAuthorizationUnknown

The port's authorization state for receive operations is unknown.


### -field NdisPortAuthorized

The port is authorized for receive operations.


### -field NdisPortUnauthorized

The port is not authorized for receive operations.


### -field NdisPortReauthorizing

The port is re-authorizing for receive operations.

</dd>
</dl>

## -remarks
The NDIS_PORT_AUTHENTICATION_PARAMETERS structure is used in 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
    OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a> OID requests to specify the current authentication state of
    an NDIS port.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-port-authentication-parameters">
   OID_GEN_PORT_AUTHENTICATION_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_PORT_AUTHENTICATION_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


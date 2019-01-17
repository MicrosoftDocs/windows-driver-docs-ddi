---
UID: NE:fwpsk.FWPS_FIELDS_RPC_EPMAP_
title: FWPS_FIELDS_RPC_EPMAP_
description: The FWPS_FIELDS_RPC_EPMAP enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_EPMAP run-time filtering layer.
old-location: netvista\fwps_fields_rpc_epmap.htm
tech.root: netvista
ms.assetid: 78960e0c-6b27-4331-a0e0-3f7ba13a54cf
ms.date: 05/02/2018
ms.keywords: FWPS_FIELDS_RPC_EPMAP, FWPS_FIELDS_RPC_EPMAP enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_RPC_EPMAP_, FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL, FWPS_FIELD_RPC_EPMAP_AUTH_TYPE, FWPS_FIELD_RPC_EPMAP_IF_UUID, FWPS_FIELD_RPC_EPMAP_IF_VERSION, FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4, FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6, FWPS_FIELD_RPC_EPMAP_LOCAL_PORT, FWPS_FIELD_RPC_EPMAP_MAX, FWPS_FIELD_RPC_EPMAP_PIPE, FWPS_FIELD_RPC_EPMAP_PROTOCOL, FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4, FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6, FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN, FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM, FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE, fwpsk/FWPS_FIELDS_RPC_EPMAP, fwpsk/FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL, fwpsk/FWPS_FIELD_RPC_EPMAP_AUTH_TYPE, fwpsk/FWPS_FIELD_RPC_EPMAP_IF_UUID, fwpsk/FWPS_FIELD_RPC_EPMAP_IF_VERSION, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_PORT, fwpsk/FWPS_FIELD_RPC_EPMAP_MAX, fwpsk/FWPS_FIELD_RPC_EPMAP_PIPE, fwpsk/FWPS_FIELD_RPC_EPMAP_PROTOCOL, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN, fwpsk/FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM, fwpsk/FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE, netvista.fwps_fields_rpc_epmap, wfp_ref_5_const_3_data_fields_64131f70-58be-4569-913f-fc651c8bab8f.xml
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows Vista.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fwpsk.h
api_name:
-	FWPS_FIELDS_RPC_EPMAP
product:
- Windows
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_EPMAP
---

# FWPS_FIELDS_RPC_EPMAP_ enumeration


## -description


The FWPS_FIELDS_RPC_EPMAP enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_EPMAP 
  <a href="https://msdn.microsoft.com/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -enum-fields




### -field FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN

The identification of the remote user.


### -field FWPS_FIELD_RPC_EPMAP_IF_UUID

The UUID of the RPC interface.


### -field FWPS_FIELD_RPC_EPMAP_IF_VERSION

The version of the RPC interface.


### -field FWPS_FIELD_RPC_EPMAP_PROTOCOL

The possible condition values are:

<ul><li>RPC_PROTSEQ_TCP</li><li>RPC_PROTSEQ_HTTP</li><li>RPC_PROTSEQ_NMP</li></ul>


### -field FWPS_FIELD_RPC_EPMAP_AUTH_TYPE

The authentication service type. For more information about authentication service types, see
     Authentication-Service Constants in the RPC section of the Microsoft Windows SDK documentation.


### -field FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL

The authentication service level. For more information about authentication service levels, see
     Authentication-Service Constants in the RPC section of the Windows SDK documentation.


### -field FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM

The certificate-based security service provider interface (SSPI) encryption algorithm.


### -field FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE

The certificate-based SSPI encryption key size.


### -field FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4

The local IPv4 address.


### -field FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6

The local IPv6 address.


### -field FWPS_FIELD_RPC_EPMAP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_RPC_EPMAP_PIPE

The name of the remote named pipe.


### -field FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4

The remote IPv4 address.


### -field FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6

The remote IPv6 address.


### -field FWPS_FIELD_RPC_EPMAP_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


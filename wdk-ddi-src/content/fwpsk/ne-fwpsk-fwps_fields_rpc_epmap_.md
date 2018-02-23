---
UID: NE:fwpsk.FWPS_FIELDS_RPC_EPMAP_
title: FWPS_FIELDS_RPC_EPMAP_
author: windows-driver-content
description: The FWPS_FIELDS_RPC_EPMAP enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_EPMAP run-time filtering layer.
old-location: netvista\fwps_fields_rpc_epmap.htm
old-project: netvista
ms.assetid: 78960e0c-6b27-4331-a0e0-3f7ba13a54cf
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FWPS_FIELD_RPC_EPMAP_PROTOCOL, fwpsk/FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM, FWPS_FIELD_RPC_EPMAP_LOCAL_PORT, FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE, fwpsk/FWPS_FIELD_RPC_EPMAP_IF_UUID, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4, FWPS_FIELD_RPC_EPMAP_IF_UUID, fwpsk/FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL, FWPS_FIELD_RPC_EPMAP_MAX, FWPS_FIELD_RPC_EPMAP_IF_VERSION, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN, FWPS_FIELD_RPC_EPMAP_PIPE, FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6, FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN, FWPS_FIELD_RPC_EPMAP_AUTH_TYPE, fwpsk/FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6, FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4, fwpsk/FWPS_FIELDS_RPC_EPMAP, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_PORT, FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4, FWPS_FIELDS_RPC_EPMAP_, fwpsk/FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE, fwpsk/FWPS_FIELD_RPC_EPMAP_PIPE, fwpsk/FWPS_FIELD_RPC_EPMAP_MAX, FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6, FWPS_FIELDS_RPC_EPMAP, fwpsk/FWPS_FIELD_RPC_EPMAP_AUTH_TYPE, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4, netvista.fwps_fields_rpc_epmap, FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM, fwpsk/FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6, fwpsk/FWPS_FIELD_RPC_EPMAP_PROTOCOL, FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL, wfp_ref_5_const_3_data_fields_64131f70-58be-4569-913f-fc651c8bab8f.xml, fwpsk/FWPS_FIELD_RPC_EPMAP_IF_VERSION, FWPS_FIELDS_RPC_EPMAP enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	fwpsk.h
apiname:
-	FWPS_FIELDS_RPC_EPMAP
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_EPMAP
---

# FWPS_FIELDS_RPC_EPMAP_ enumeration


## -description


The FWPS_FIELDS_RPC_EPMAP enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_EPMAP 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_RPC_EPMAP_ { 
  FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN,
  FWPS_FIELD_RPC_EPMAP_IF_UUID,
  FWPS_FIELD_RPC_EPMAP_IF_VERSION,
  FWPS_FIELD_RPC_EPMAP_PROTOCOL,
  FWPS_FIELD_RPC_EPMAP_AUTH_TYPE,
  FWPS_FIELD_RPC_EPMAP_AUTH_LEVEL,
  FWPS_FIELD_RPC_EPMAP_SEC_ENCRYPT_ALGORITHM,
  FWPS_FIELD_RPC_EPMAP_SEC_KEY_SIZE,
  FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V4,
  FWPS_FIELD_RPC_EPMAP_LOCAL_ADDR_V6,
  FWPS_FIELD_RPC_EPMAP_LOCAL_PORT,
  FWPS_FIELD_RPC_EPMAP_PIPE,
  FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V4,
  FWPS_FIELD_RPC_EPMAP_REMOTE_ADDR_V6,
  FWPS_FIELD_RPC_EPMAP_MAX
} FWPS_FIELDS_RPC_EPMAP;
````


## -enum-fields




### -field FWPS_FIELD_RPC_EPMAP_REMOTE_USER_TOKEN

The identification of the remote user.


### -field FWPS_FIELD_RPC_EPMAP_IF_UUID

The UUID of the RPC interface.


### -field FWPS_FIELD_RPC_EPMAP_IF_VERSION

The version of the RPC interface.


### -field FWPS_FIELD_RPC_EPMAP_PROTOCOL



#####  The possible condition values are:



#### RPC_PROTSEQ_TCP



#### RPC_PROTSEQ_HTTP



#### RPC_PROTSEQ_NMP


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


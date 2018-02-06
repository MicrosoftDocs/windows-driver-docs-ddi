---
UID: NE:fwpsk.FWPS_FIELDS_RPC_PROXY_CONN_
title: FWPS_FIELDS_RPC_PROXY_CONN_
author: windows-driver-content
description: The FWPS_FIELDS_RPC_PROXY_CONN enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_PROXY_CONN run-time filtering layer.
old-location: netvista\fwps_fields_rpc_proxy_conn.htm
old-project: netvista
ms.assetid: 22d60d8c-dad0-4b2c-9ae7-0e30552f5a81
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.fwps_fields_rpc_proxy_conn, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT, FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME, FWPS_FIELDS_RPC_PROXY_CONN, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH, FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_MAX, FWPS_FIELDS_RPC_PROXY_CONN_, fwpsk/FWPS_FIELDS_RPC_PROXY_CONN, FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID, FWPS_FIELDS_RPC_PROXY_CONN enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN, FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT, wfp_ref_5_const_3_data_fields_3fa5702b-041e-45d8-a9d1-0271f06a3a2e.xml, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN, FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE, FWPS_FIELD_RPC_PROXY_CONN_MAX, fwpsk/FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE
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
-	FWPS_FIELDS_RPC_PROXY_CONN
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_PROXY_CONN
---

# FWPS_FIELDS_RPC_PROXY_CONN_ enumeration


## -description


The FWPS_FIELDS_RPC_PROXY_CONN enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_PROXY_CONN 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_RPC_PROXY_CONN_ { 
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN,
  FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME,
  FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT,
  FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE,
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH,
  FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID,
  FWPS_FIELD_RPC_PROXY_CONN_MAX
} FWPS_FIELDS_RPC_PROXY_CONN;
````


## -enum-fields




### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_TOKEN

The identification of the client when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_SERVER_NAME

The name of the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_SERVER_PORT

The port on the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_CONN_PROXY_AUTH_TYPE

The RPC proxy authentication service type. For more information about authentication service
     types, see Authentication-Service Constants in the RPC section of the Windows SDK.


### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_KEY_LENGTH

The secure socket layer (SSL) key length in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_CONN_CLIENT_CERT_OID

The object identifier (OID) in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_CONN_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


---
UID: NE:fwpsk.FWPS_FIELDS_RPC_PROXY_IF_
title: FWPS_FIELDS_RPC_PROXY_IF_
author: windows-driver-content
description: The FWPS_FIELDS_RPC_PROXY_IF_IF enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_PROXY_IF run-time filtering layer.
old-location: netvista\fwps_fields_rpc_proxy_if_if.htm
old-project: netvista
ms.assetid: 60389be9-8cda-40cf-b02a-c13a2d17091f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: wfp_ref_5_const_3_data_fields_666debd4-c19e-4dcd-91d9-024f298b342f.xml, FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT, FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH, fwpsk/FWPS_FIELD_RPC_PROXY_IF_IF_UUID, FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE, FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME, fwpsk/FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME, netvista.fwps_fields_rpc_proxy_if_if, FWPS_FIELDS_RPC_PROXY_IF_IF, FWPS_FIELDS_RPC_PROXY_IF_IF enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_RPC_PROXY_IF_IF_UUID, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH, FWPS_FIELD_RPC_PROXY_IF_MAX, FWPS_FIELDS_RPC_PROXY_IF_, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN, fwpsk/FWPS_FIELD_RPC_PROXY_IF_MAX, fwpsk/FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE, FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN, FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID, fwpsk/FWPS_FIELD_RPC_PROXY_IF_IF_VERSION, FWPS_FIELD_RPC_PROXY_IF_IF_VERSION, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID, fwpsk/FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT, fwpsk/FWPS_FIELDS_RPC_PROXY_IF_IF
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
-	FWPS_FIELDS_RPC_PROXY_IF_IF
product: Windows
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_PROXY_IF_IF
---

# FWPS_FIELDS_RPC_PROXY_IF_ enumeration


## -description


The FWPS_FIELDS_RPC_PROXY_IF_IF enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_PROXY_IF 
  <a href="https://msdn.microsoft.com/en-us/library/windows/desktop/aa366492">run-time filtering layer</a>.


## -syntax


````
typedef enum FWPS_FIELDS_RPC_PROXY_IF_ { 
  FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN,
  FWPS_FIELD_RPC_PROXY_IF_IF_UUID,
  FWPS_FIELD_RPC_PROXY_IF_IF_VERSION,
  FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME,
  FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT,
  FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE,
  FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH,
  FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID,
  FWPS_FIELD_RPC_PROXY_IF_MAX
} FWPS_FIELDS_RPC_PROXY_IF_IF;
````


## -enum-fields




### -field FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN

The identification of the client when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_IF_IF_UUID

The UUID of the RPC interface.


### -field FWPS_FIELD_RPC_PROXY_IF_IF_VERSION

The version of the RPC interface.


### -field FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME

The name of the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT

The port on the RPC server when using RpcProxy.


### -field FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE

The RPC proxy authentication service type. For more information about authentication service
     types, see Authentication-Service Constants in the RPC section of the Windows SDK documentation.


### -field FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH

The secure socket layer (SSL) key length in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID

The object identifier (OID) in the client certificate.


### -field FWPS_FIELD_RPC_PROXY_IF_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


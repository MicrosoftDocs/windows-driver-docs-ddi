---
UID: NE:fwpsk.FWPS_FIELDS_RPC_PROXY_IF_
title: FWPS_FIELDS_RPC_PROXY_IF_ (fwpsk.h)
description: The FWPS_FIELDS_RPC_PROXY_IF_IF enumeration type specifies the data field identifiers for the FWPS_LAYER_RPC_PROXY_IF run-time filtering layer.
old-location: netvista\fwps_fields_rpc_proxy_if_if.htm
tech.root: netvista
ms.assetid: 60389be9-8cda-40cf-b02a-c13a2d17091f
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_RPC_PROXY_IF_ enumeration"]
ms.keywords: FWPS_FIELDS_RPC_PROXY_IF_, FWPS_FIELDS_RPC_PROXY_IF_IF, FWPS_FIELDS_RPC_PROXY_IF_IF enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH, FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID, FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN, FWPS_FIELD_RPC_PROXY_IF_IF_UUID, FWPS_FIELD_RPC_PROXY_IF_IF_VERSION, FWPS_FIELD_RPC_PROXY_IF_MAX, FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE, FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME, FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT, fwpsk/FWPS_FIELDS_RPC_PROXY_IF_IF, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_KEY_LENGTH, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_CERT_OID, fwpsk/FWPS_FIELD_RPC_PROXY_IF_CLIENT_TOKEN, fwpsk/FWPS_FIELD_RPC_PROXY_IF_IF_UUID, fwpsk/FWPS_FIELD_RPC_PROXY_IF_IF_VERSION, fwpsk/FWPS_FIELD_RPC_PROXY_IF_MAX, fwpsk/FWPS_FIELD_RPC_PROXY_IF_PROXY_AUTH_TYPE, fwpsk/FWPS_FIELD_RPC_PROXY_IF_SERVER_NAME, fwpsk/FWPS_FIELD_RPC_PROXY_IF_SERVER_PORT, netvista.fwps_fields_rpc_proxy_if_if, wfp_ref_5_const_3_data_fields_666debd4-c19e-4dcd-91d9-024f298b342f.xml
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
targetos: Windows
req.typenames: FWPS_FIELDS_RPC_PROXY_IF_IF
f1_keywords:
 - FWPS_FIELDS_RPC_PROXY_IF_
 - fwpsk/FWPS_FIELDS_RPC_PROXY_IF_
 - FWPS_FIELDS_RPC_PROXY_IF_IF
 - fwpsk/FWPS_FIELDS_RPC_PROXY_IF_IF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_RPC_PROXY_IF_IF
---

# FWPS_FIELDS_RPC_PROXY_IF_ enumeration


## -description

The FWPS_FIELDS_RPC_PROXY_IF_IF enumeration type specifies the data field identifiers for the
  FWPS_LAYER_RPC_PROXY_IF 
  <a href="https://docs.microsoft.com/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.

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


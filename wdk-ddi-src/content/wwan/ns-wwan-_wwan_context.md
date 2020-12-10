---
UID: NS:wwan._WWAN_CONTEXT
title: _WWAN_CONTEXT (wwan.h)
description: The WWAN_CONTEXT structure represents a provisioned context that is supported by the MB device.
old-location: netvista\wwan_context.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_CONTEXT structure"]
ms.keywords: "*PWWAN_CONTEXT, PWWAN_CONTEXT, PWWAN_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], WWAN_CONTEXT, WWAN_CONTEXT structure [Network Drivers Starting with Windows Vista], WwanRef_6700da85-2a7a-4712-86e8-fb40e11e42a1.xml, _WWAN_CONTEXT, netvista.wwan_context, wwan/PWWAN_CONTEXT, wwan/WWAN_CONTEXT"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.typenames: WWAN_CONTEXT, *PWWAN_CONTEXT
f1_keywords:
 - _WWAN_CONTEXT
 - wwan/_WWAN_CONTEXT
 - PWWAN_CONTEXT
 - wwan/PWWAN_CONTEXT
 - WWAN_CONTEXT
 - wwan/WWAN_CONTEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_CONTEXT
---

# _WWAN_CONTEXT structure


## -description

The WWAN_CONTEXT structure represents a provisioned context that is supported by the MB
  device.

## -struct-fields

### -field ContextId

A unique ID for this context.
     

For 
     <i>set</i> OID_WWAN_PROVISIONED_CONTEXT requests, the MB Service can set the value to
     WWAN_CONTEXT_ID_APPEND. If this value is used, the miniport driver should decide the index for storing
     the context information. WWAN_CONTEXT_ID_APPEND should never be returned in response to 
     <i>query</i> OID_WWAN_PROVISIONED_CONTEXT requests.

### -field ContextType

Specifies the type of context being represented, for example, Internet connectivity, VPN (a
     connection to a corporate network), or Voice-over-IP (VOIP). Miniport drivers should specify 
     <b>WwanContextTypeNone</b> for empty or unprovisioned contexts.

### -field AccessString

A NULL-terminated string to access the network. For GSM-based networks, this would be an Access
     Point Name (APN) string such as "data.thephone-company.com". For CDMA-based networks, this might be a
     special dial code such as "#777" or a Network Access Identifier (NAI) such as
     "foo@thephone-company.com". This member can be <b>NULL</b>.
     

The size of the string should not exceed 100 bytes.

### -field UserName

The username to use for authentication. This member can be <b>NULL</b>.

### -field Password

The password to use for authentication. This member can be <b>NULL</b>.

### -field Compression

Specifies the compression to be used in the data connection for header and data. This member
     applies only to GSM-based devices. The MB Service sets this member to 
     <b>WwanCompressionNone</b> for CDMA-based devices.

### -field AuthType

Authentication type to use for the PDP activation.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_set_provisioned_context">
   NDIS_WWAN_SET_PROVISIONED_CONTEXT</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_auth_protocol">WWAN_AUTH_PROTOCOL</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_compression">WWAN_COMPRESSION</a>



<a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_context_type">WWAN_CONTEXT_TYPE</a>

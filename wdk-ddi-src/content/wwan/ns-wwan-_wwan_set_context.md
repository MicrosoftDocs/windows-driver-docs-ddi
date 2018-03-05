---
UID: NS:wwan._WWAN_SET_CONTEXT
title: "_WWAN_SET_CONTEXT"
author: windows-driver-content
description: The WWAN_SET_CONTEXT structure represents a provisioned context with a network provider identification that is supported by the MB device.
old-location: netvista\wwan_set_context.htm
old-project: netvista
ms.assetid: 00772a37-ef1b-446b-b7bd-1a6aa27d1dad
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_SET_CONTEXT, PWWAN_SET_CONTEXT, PWWAN_SET_CONTEXT structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_CONTEXT, WWAN_SET_CONTEXT structure [Network Drivers Starting with Windows Vista], WwanRef_08361ced-712a-464d-b374-7b18a096b8e5.xml, _WWAN_SET_CONTEXT, netvista.wwan_set_context, wwan/PWWAN_SET_CONTEXT, wwan/WWAN_SET_CONTEXT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_SET_CONTEXT
product: Windows
targetos: Windows
req.typenames: WWAN_SET_CONTEXT, *PWWAN_SET_CONTEXT
req.product: Windows 10 or later.
---

# _WWAN_SET_CONTEXT structure


## -description


The WWAN_SET_CONTEXT structure represents a provisioned context with a network provider
  identification that is supported by the MB device.


## -syntax


````
typedef struct _WWAN_SET_CONTEXT {
  ULONG              ContextId;
  WWAN_CONTEXT_TYPE  ContextType;
  WCHAR              AccessString[WWAN_ACCESSSTRING_LEN];
  WCHAR              UserName[WWAN_USERNAME_LEN];
  WCHAR              Password[WWAN_PASSWORD_LEN];
  WWAN_COMPRESSION   Compression;
  WWAN_AUTH_PROTOCOL AuthType;
  WCHAR              ProviderId[WWAN_PROVIDERID_LEN];
} WWAN_SET_CONTEXT, *PWWAN_SET_CONTEXT;
````


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


### -field ProviderId

A NULL-terminated string that represents the network provider identification for which the
     provisioned context should be stored in 
     <i>set</i> OID_WWAN_PROVISIONED_CONTEXT requests. Miniport drivers should return the added provisioned
     context in response to subsequent 
     <i>query</i> operations when a Subscriber Identity Module (SIM card) with this home provider ID is in the
     device.


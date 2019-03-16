---
UID: NE:netconfiguration._NET_CONFIGURATION_QUERY_ULONG_FLAGS
title: _NET_CONFIGURATION_QUERY_ULONG_FLAGS (netconfiguration.h)
description: The NET_CONFIGURATION_QUERY_ULONG_FLAGS enumeration is used as an input parameter to the NetConfigurationQueryUlong method.
tech.root: netvista
ms.assetid: fd0f43ac-4895-4fe7-9eb3-7b4d7a8c052e
ms.date: 02/07/2018
ms.topic: enum
ms.keywords: _NET_CONFIGURATION_QUERY_ULONG_FLAGS, NET_CONFIGURATION_QUERY_ULONG_FLAGS, 
req.header: netconfiguration.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_CONFIGURATION_QUERY_ULONG_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- netconfiguration.h
api_name: 
- NET_CONFIGURATION_QUERY_ULONG_FLAGS
product:
- Windows
targetos: Windows
product:
- Windows
---

# _NET_CONFIGURATION_QUERY_ULONG_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1903.

The **NET_CONFIGURATION_QUERY_ULONG_FLAGS** enumeration is used as an input parameter to the [NetConfigurationQueryUlong](nf-netconfiguration-netconfigurationqueryulong.md) method.

## -enum-fields

### -field NET_CONFIGURATION_QUERY_ULONG_NO_FLAGS : 
No flags are set.

### -field NET_CONFIGURATION_QUERY_ULONG_MAY_BE_STORED_AS_HEX_STRING : 
Specifies that the ULONG may be stored in the configuration database as a string in hex format.

## -remarks


## -see-also

[NetConfigurationQueryUlong](nf-netconfiguration-netconfigurationqueryulong.md)

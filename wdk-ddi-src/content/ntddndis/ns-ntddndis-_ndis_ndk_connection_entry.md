---
UID: NS:ntddndis._NDIS_NDK_CONNECTION_ENTRY
title: _NDIS_NDK_CONNECTION_ENTRY (ntddndis.h)
description: The NDIS_NDK_CONNECTION_ENTRY structure specifies a connection entry for an active NDK connection on a miniport adapter.
old-location: netvista\ndis_ndk_connection_entry.htm
tech.root: netvista
ms.assetid: 58BA2AE1-9F48-4B3B-A545-EECC9B3E858C
ms.date: 05/02/2018
keywords: ["NDIS_NDK_CONNECTION_ENTRY structure"]
ms.keywords: NDIS_NDK_CONNECTION_ENTRY, NDIS_NDK_CONNECTION_ENTRY structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_CONNECTION_ENTRY, PNDIS_NDK_CONNECTION_ENTRY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_CONNECTION_ENTRY, netvista.ndis_ndk_connection_entry, ntddndis/NDIS_NDK_CONNECTION_ENTRY, ntddndis/PNDIS_NDK_CONNECTION_ENTRY
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.typenames: NDIS_NDK_CONNECTION_ENTRY
f1_keywords:
 - _NDIS_NDK_CONNECTION_ENTRY
 - ntddndis/_NDIS_NDK_CONNECTION_ENTRY
 - NDIS_NDK_CONNECTION_ENTRY
 - ntddndis/NDIS_NDK_CONNECTION_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_NDK_CONNECTION_ENTRY
---

# _NDIS_NDK_CONNECTION_ENTRY structure


## -description

The <b>NDIS_NDK_CONNECTION_ENTRY</b> structure specifies a connection entry for an active NDK connection on a miniport adapter.

## -struct-fields

### -field Local

The local IP address and port.

### -field Remote

The remote IP address and port.

### -field UserModeOwner

A BOOLEAN value that is TRUE if the connection is an NDS user-mode connection, or FALSE if it is an NDK kernel-mode connection.

### -field OwnerPid

A process identifier for an NDS user-mode connection.

## -remarks

The NDIS_NDK_CONNECTION_ENTRY structure is used in the <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_connections">NDIS_NDK_CONNECTIONS</a> structure to specify an array of connections.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_connections">NDIS_NDK_CONNECTIONS</a>
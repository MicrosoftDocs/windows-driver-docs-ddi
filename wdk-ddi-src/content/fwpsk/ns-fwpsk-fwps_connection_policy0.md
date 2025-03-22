---
UID: NS:fwpsk._FWPS_CONNECTION_POLICY0
tech.root: netvista
title: FWPS_CONNECTION_POLICY0
ms.date: 03/22/2024
targetos: Windows
description: The FWPS_CONNECTION_POLICY0 structure defines the connection policy for outbound network connections. 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: fwpsk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: FWPS_CONNECTION_POLICY0
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - _FWPS_CONNECTION_POLICY0
 - FWPS_CONNECTION_POLICY0
f1_keywords:
 - _FWPS_CONNECTION_POLICY0
 - fwpsk/_FWPS_CONNECTION_POLICY0
 - FWPS_CONNECTION_POLICY0
 - fwpsk/FWPS_CONNECTION_POLICY0
dev_langs:
 - c++
helpviewer_keywords:
 - _FWPS_CONNECTION_POLICY0
---

# FWPS_CONNECTION_POLICY0 structure (fwpsk.h)

## -description

The **FWPS_CONNECTION_POLICY0** structure defines the connection policy for outbound network connections. 

## -struct-fields

### -field localAddress

The local address of the outbound connection. This is an IPV4 or IPV6 address and TCP/UDP port formatted as a [**SOCKADDR_STORAGE**](/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh) structure.

### -field nextHopAddress

The next hop address for the outbound connection. This is an IPV4 or IPV6 address and TCP/UDP port formatted as a [**SOCKADDR_STORAGE**](/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh) structure.

### -field interfaceLuid

The locally unique identifier (LUID) for the network interface used for the outbound connection.

## -remarks

## -see-also

[**SOCKADDR_STORAGE**](/windows/win32/api/ws2def/ns-ws2def-sockaddr_storage_lh)


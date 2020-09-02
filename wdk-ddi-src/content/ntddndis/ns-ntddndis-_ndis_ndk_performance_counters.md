---
UID: NS:ntddndis._NDIS_NDK_PERFORMANCE_COUNTERS
title: _NDIS_NDK_PERFORMANCE_COUNTERS (ntddndis.h)
description: The NDIS_NDK_PERFORMANCE_COUNTERS structure contains the NDK performance counters.
old-location: netvista\ndis_ndk_performance_counters.htm
tech.root: netvista
ms.assetid: DA752989-B49B-4832-8821-8B45AB3304CD
ms.date: 05/02/2018
keywords: ["NDIS_NDK_PERFORMANCE_COUNTERS structure"]
ms.keywords: "*PNDIS_NDK_PERFORMANCE_COUNTERS, NDIS_NDK_PERFORMANCE_COUNTERS, NDIS_NDK_PERFORMANCE_COUNTERS structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_PERFORMANCE_COUNTERS, PNDIS_NDK_PERFORMANCE_COUNTERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_PERFORMANCE_COUNTERS, netvista.ndis_ndk_performance_counters, ntddndis/NDIS_NDK_PERFORMANCE_COUNTERS, ntddndis/PNDIS_NDK_PERFORMANCE_COUNTERS"
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
req.typenames: NDIS_NDK_PERFORMANCE_COUNTERS, *PNDIS_NDK_PERFORMANCE_COUNTERS
f1_keywords:
 - _NDIS_NDK_PERFORMANCE_COUNTERS
 - ntddndis/_NDIS_NDK_PERFORMANCE_COUNTERS
 - PNDIS_NDK_PERFORMANCE_COUNTERS
 - ntddndis/PNDIS_NDK_PERFORMANCE_COUNTERS
 - NDIS_NDK_PERFORMANCE_COUNTERS
 - ntddndis/NDIS_NDK_PERFORMANCE_COUNTERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_NDK_PERFORMANCE_COUNTERS
---

# _NDIS_NDK_PERFORMANCE_COUNTERS structure


## -description

The <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure contains the NDK performance counters.

## -struct-fields

### -field Connect

The number of outbound connections established. In a bitmask of counters (for example, <b>MissingCounterMask</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a> structure), this is counter 0.

### -field Accept

The number of inbound <i>RDMA</i> connections established. In a bitmask of counters (for example, <b>MissingCounterMask</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a> structure), this is counter 1.

### -field ConnectFailure

The  number of inbound and outbound <i>RDMA</i> connect attempts that  failed. In a bitmask of counters, this is counter 2.

### -field ConnectionError

The number of established connections with  an error before a consumer disconnected the connection. In a bitmask of counters, this is counter 3.

### -field ActiveConnection

The number of  active <i>RDMA</i> connections. In a bitmask of counters, this is counter 4.

### -field Reserved01

Reserved.

### -field Reserved02

Reserved.

### -field Reserved03

Reserved.

### -field Reserved04

Reserved.

### -field Reserved05

Reserved.

### -field Reserved06

Reserved.

### -field Reserved07

Reserved.

### -field Reserved08

Reserved.

### -field Reserved09

Reserved.

### -field Reserved10

Reserved.

### -field Reserved11

Reserved.

### -field Reserved12

Reserved.

### -field Reserved13

Reserved.

### -field Reserved14

Reserved.

### -field Reserved15

Reserved.

### -field Reserved16

Reserved.

### -field Reserved17

Reserved.

### -field Reserved18

Reserved.

### -field Reserved19

Reserved.

### -field Reserved20

Reserved.

### -field CQError

The number of <i>RDMA</i> completion queue (CQs) that went into an error state. In a bitmask of counters, this is counter 25.

### -field RDMAInOctets

The number of bytes  for all incoming <i>RDMA</i> traffic. This should include additional layer two protocol overhead.  In a bitmask of counters, this is counter 26.

### -field RDMAOutOctets

The number of bytes  for all outgoing <i>RDMA</i> traffic.  This should include additional layer two protocol overhead.  In a bitmask of counters, this is counter 27.

### -field RDMAInFrames

The number, in frames,  of layer two frames that carry incoming <i>RDMA</i> traffic. In a bitmask of counters, this is counter 28.

### -field RDMAOutFrames

The number, in frames,  of layer two frames that carry outgoing <i>RDMA</i> traffic. In a bitmask of counters, this is counter 29.

## -remarks

The <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure is used in the <b>CounterSet</b>  member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_statistics_info">NDIS_NDK_STATISTICS_INFO</a> structure. 

NDK providers are required to support all the performance counters that are included
    in the <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure. However, in the rare case that
    a provider cannot support a counter due to extreme implementation difficulties,
    the provider must indicate any unsupported counters with the mask value for the
    counter which it cannot support. The <b>MissingCounterMask</b>  parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a> structure specifies a bitmask that identifies counters that an NDK provider does not support.

All <b>ReservedXX</b> counters must be set to zero by providers and are ignored by NDIS. The term <i>RDMA</i> refers to all NDKPI and NDSPI activity as well as activity through any other RDMA programming interface that might be exposed by the provider. All providers must report the NDKPI and NDSPI activity with these counters, but reporting activity for other RDMA programming interfaces is not a strict requirement. The term <i>RDMA traffic</i> for the RDMA in, out, byte, and frame counters refers to all RDMA activity originating from NDKPI, NDSPI, and other RDMA programming interfaces (if any). This includes reads and writes (that is, direct data placement) as well as sends and receives. This also should also include all of the associated layer two protocol overhead. That is, <i>RDMA traffic</i> on an NDK-capable adapter includes all traffic through the adapter except for traffic that is  delivered through the standard NDIS send and receive interface and TCP chimney by NDIS protocol drivers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_capabilities">NDIS_NDK_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_ndk_statistics_info">NDIS_NDK_STATISTICS_INFO</a>


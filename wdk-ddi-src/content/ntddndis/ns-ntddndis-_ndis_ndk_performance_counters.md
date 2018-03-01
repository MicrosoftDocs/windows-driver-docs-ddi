---
UID: NS:ntddndis._NDIS_NDK_PERFORMANCE_COUNTERS
title: "_NDIS_NDK_PERFORMANCE_COUNTERS"
author: windows-driver-content
description: The NDIS_NDK_PERFORMANCE_COUNTERS structure contains the NDK performance counters.
old-location: netvista\ndis_ndk_performance_counters.htm
old-project: netvista
ms.assetid: DA752989-B49B-4832-8821-8B45AB3304CD
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_NDK_PERFORMANCE_COUNTERS, NDIS_NDK_PERFORMANCE_COUNTERS, NDIS_NDK_PERFORMANCE_COUNTERS structure [Network Drivers Starting with Windows Vista], PNDIS_NDK_PERFORMANCE_COUNTERS, PNDIS_NDK_PERFORMANCE_COUNTERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NDK_PERFORMANCE_COUNTERS, netvista.ndis_ndk_performance_counters, ntddndis/NDIS_NDK_PERFORMANCE_COUNTERS, ntddndis/PNDIS_NDK_PERFORMANCE_COUNTERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_NDK_PERFORMANCE_COUNTERS
product: Windows
targetos: Windows
req.typenames: NDIS_NDK_PERFORMANCE_COUNTERS, *PNDIS_NDK_PERFORMANCE_COUNTERS
---

# _NDIS_NDK_PERFORMANCE_COUNTERS structure


## -description


The <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure contains the NDK performance counters. 


## -syntax


````
typedef struct _NDIS_NDK_PERFORMANCE_COUNTERS {
  ULONG64 Connect;
  ULONG64 Accept;
  ULONG64 ConnectFailure;
  ULONG64 ConnectionError;
  ULONG64 ActiveConnection;
  ULONG64 Reserved01;
  ULONG64 Reserved02;
  ULONG64 Reserved03;
  ULONG64 Reserved04;
  ULONG64 Reserved05;
  ULONG64 Reserved06;
  ULONG64 Reserved07;
  ULONG64 Reserved08;
  ULONG64 Reserved09;
  ULONG64 Reserved10;
  ULONG64 Reserved11;
  ULONG64 Reserved12;
  ULONG64 Reserved13;
  ULONG64 Reserved14;
  ULONG64 Reserved15;
  ULONG64 Reserved16;
  ULONG64 Reserved17;
  ULONG64 Reserved18;
  ULONG64 Reserved19;
  ULONG64 Reserved20;
  ULONG64 CQError;
  ULONG64 RDMAInOctets;
  ULONG64 RDMAOutOctets;
  ULONG64 RDMAInFrames;
  ULONG64 RDMAOutFrames;
} NDIS_NDK_PERFORMANCE_COUNTERS, *PNDIS_NDK_PERFORMANCE_COUNTERS;
````


## -struct-fields




### -field Connect

The number of outbound connections established. In a bitmask of counters (for example, <b>MissingCounterMask</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_capabilities.md">NDIS_NDK_CAPABILITIES</a> structure), this is counter 0.


### -field Accept

The number of inbound <i>RDMA</i> connections established. In a bitmask of counters (for example, <b>MissingCounterMask</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_capabilities.md">NDIS_NDK_CAPABILITIES</a> structure), this is counter 1.


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



The <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure is used in the <b>CounterSet</b>  member of the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_statistics_info.md">NDIS_NDK_STATISTICS_INFO</a> structure. 

NDK providers are required to support all the performance counters that are included
    in the <b>NDIS_NDK_PERFORMANCE_COUNTERS</b> structure. However, in the rare case that
    a provider cannot support a counter due to extreme implementation difficulties,
    the provider must indicate any unsupported counters with the mask value for the
    counter which it cannot support. The <b>MissingCounterMask</b>  parameter of the <a href="..\ntddndis\ns-ntddndis-_ndis_ndk_capabilities.md">NDIS_NDK_CAPABILITIES</a> structure specifies a bitmask that identifies counters that an NDK provider does not support.

All <b>ReservedXX</b> counters must be set to zero by providers and are ignored by NDIS. The term <i>RDMA</i> refers to all NDKPI and NDSPI activity as well as activity through any other RDMA programming interface that might be exposed by the provider. All providers must report the NDKPI and NDSPI activity with these counters, but reporting activity for other RDMA programming interfaces is not a strict requirement. The term <i>RDMA traffic</i> for the RDMA in, out, byte, and frame counters refers to all RDMA activity originating from NDKPI, NDSPI, and other RDMA programming interfaces (if any). This includes reads and writes (that is, direct data placement) as well as sends and receives. This also should also include all of the associated layer two protocol overhead. That is, <i>RDMA traffic</i> on an NDK-capable adapter includes all traffic through the adapter except for traffic that is  delivered through the standard NDIS send and receive interface and TCP chimney by NDIS protocol drivers.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_ndk_statistics_info.md">NDIS_NDK_STATISTICS_INFO</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_ndk_capabilities.md">NDIS_NDK_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NDK_PERFORMANCE_COUNTERS structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


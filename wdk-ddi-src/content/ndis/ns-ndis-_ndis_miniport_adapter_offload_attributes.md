---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES"
author: windows-driver-content
description: An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure to define task offload and connection offload attributes, if any, that are associated with a miniport adapter.
old-location: netvista\ndis_miniport_adapter_offload_attributes.htm
tech.root: netvista
ms.assetid: 9ce875fc-ed3f-43e9-bfbc-081f02cb1999
ms.date: 05/02/2018
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, miniport_structures_ref_71ee0bdb-903e-4554-915b-010abe803fb3.xml, ndis/NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, netvista.ndis_miniport_adapter_offload_attributes"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	ndis.h
api_name:
-	NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure


## -description


An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure to define task
  offload and connection offload attributes, if any, that are associated with a miniport adapter.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES_REVISION_1.


### -field DefaultOffloadConfiguration

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure that indicates the
     current offload capabilities that are provided by the miniport adapter.


### -field HardwareOffloadCapabilities

A pointer to an NDIS_OFFLOAD structure that indicates all the task offload capabilites that are
     supported by the miniport adapter. These capabilities include capabilities that are currently disabled
     by standardized keywords in the registry.


### -field DefaultTcpConnectionOffloadConfiguration

A pointer to an 
     <a href="https://msdn.microsoft.com/d37a773d-0a83-4592-9c21-3ceaa6454549">
     NDIS_TCP_CONNECTION_OFFLOAD</a> structure that indicates the current connection offload capabilities
     that are provided by the miniport adapter.


### -field TcpConnectionOffloadHardwareCapabilities

A pointer to an NDIS_TCP_CONNECTION_OFFLOAD structure that indicates all the connection offload
     capabilites that are supported by the miniport adapter. These capabilities include capabilities that are
     currently disabled by standardized keywords in the registry.


## -remarks



A miniport driver that supports task offload or connection offload passes a pointer to an
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/861626af-23ea-40dc-a91a-7da42d4b0a1c">
    NdisMSetMiniportAttributes</a> function. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function
    during initialization.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559004">NDIS_TASK_OFFLOAD_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567875">NDIS_TCP_CONNECTION_OFFLOAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563672">NdisMSetMiniportAttributes</a>
 

 


---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
title: _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure specifies the receive filtering features that are enabled or disabled on a network adapter.NDIS receive filters are used in the following NDIS interfaces:NDIS Packet Coalescing.
old-location: netvista\ndis_receive_filter_global_parameters.htm
tech.root: netvista
ms.assetid: 4ec36054-ba61-4862-b185-7473a6806804
ms.date: 05/02/2018
keywords: ["NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure"]
ms.keywords: "*PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, netvista.ndis_receive_filter_global_parameters, ntddndis/NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, virtual_machine_queue_ref_b51ed6bf-8c3c-41f5-a9ef-a5ec3a720ef2.xml"
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.typenames: NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, *PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
f1_keywords:
 - _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
 - ntddndis/_NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
 - PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
 - ntddndis/PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
 - NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
 - ntddndis/NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddndis.h
api_name:
 - NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
---

# _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure


## -description

The <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure specifies the receive filtering features that are
  enabled or disabled on a network adapter.

NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="/windows-hardware/drivers/network/ndis-packet-coalescing">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/managing-packet-coalescing-receive-filters">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="/windows-hardware/drivers/network/single-root-i-o-virtualization--sr-iov-">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/setting-a-receive-filter-on-a-virtual-port">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="/windows-hardware/drivers/network/virtual-machine-queue--vmq-">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="/windows-hardware/drivers/network/setting-and-clearing-vmq-filters">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -struct-fields

### -field Header

The 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_GLOBAL_PARAMETERS_REVISION_1.

### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.

### -field EnabledFilterTypes

A  bitwise OR of flags for types of enabled receive filters. The
     following filter type flag is valid.
     





#### NDIS_RECEIVE_FILTER_VMQ_FILTERS_ENABLED

Specifies that VMQ filters are enabled.

<div class="alert"><b>Note</b>  The miniport driver should set this flag if the miniport driver is enabled to use the SR-IOV interface. For more information on how these interfaces are enabled, see <a href="/windows-hardware/drivers/network/handling-sr-iov--vmq--and-rss-standardized-inf-keywords">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.</div>
<div> </div>


#### NDIS_RECEIVE_FILTER_PACKET_COALESCING_FILTERS_ENABLED

Specifies that NDIS packet coalescing receive filters are enabled.

### -field EnabledQueueTypes

A  bitwise OR of flags for types of enabled receive queues. The
     following queue type flag is valid.
     





#### NDIS_RECEIVE_FILTER_VM_QUEUES_ENABLED

Specifies that virtual machine (VM) queues are enabled.  VM queues are used in the VMQ and SR-IOV interface.

## -remarks

The <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure is used in the 
    <a href="/windows-hardware/drivers/network/oid-receive-filter-global-parameters">
    OID_RECEIVE_FILTER_GLOBAL_PARAMETERS</a> query OID to obtain the current global receive filter
    settings.

<div class="alert"><b>Note</b>  Many of the members and flag settings of the <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure are valid if the miniport driver is enabled to use the VMQ or SR-IOV interface. The miniport driver is enabled to use these interfaces through standardized INF keywords. For more information, see <a href="/windows-hardware/drivers/network/handling-sr-iov--vmq--and-rss-standardized-inf-keywords">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/network/oid-receive-filter-global-parameters">
   OID_RECEIVE_FILTER_GLOBAL_PARAMETERS</a>
---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
title: "_NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS" (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure specifies the receive filtering features that are enabled or disabled on a network adapter.NDIS receive filters are used in the following NDIS interfaces:NDIS Packet Coalescing.
old-location: netvista\ndis_receive_filter_global_parameters.htm
tech.root: netvista
ms.assetid: 4ec36054-ba61-4862-b185-7473a6806804
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, netvista.ndis_receive_filter_global_parameters, ntddndis/NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, virtual_machine_queue_ref_b51ed6bf-8c3c-41f5-a9ef-a5ec3a720ef2.xml"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS, *PNDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS
---

# _NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure specifies the receive filtering features that are
  enabled or disabled on a network adapter.

NDIS receive filters are used in the following NDIS interfaces:
<ul>
<li>

<a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS Packet Coalescing</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/20EA71E0-B880-4891-A12E-76F4C9AB16E6">Managing Packet Coalescing Receive Filters</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/F0137D59-1701-4DFC-BB30-27E477FC0706">Setting a Receive Filter on a Virtual Port</a>.

</li>
<li>

<a href="https://msdn.microsoft.com/c502c7d6-bdf1-4656-b5a5-339250910f08">Virtual Machine Queue (VMQ)</a>. For more information about how to use receive filters in this interface, see <a href="https://msdn.microsoft.com/bfee8a3c-d2be-4718-beb4-067b66756a41">Setting and Clearing VMQ Filters</a>.

</li>
</ul>

## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
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

<div class="alert"><b>Note</b>  The miniport driver should set this flag if the miniport driver is enabled to use the SR-IOV interface. For more information on how these interfaces are enabled, see <a href="https://msdn.microsoft.com/EF556563-4097-4388-A563-29FC891AC626">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.</div>
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
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-global-parameters">
    OID_RECEIVE_FILTER_GLOBAL_PARAMETERS</a> query OID to obtain the current global receive filter
    settings.

<div class="alert"><b>Note</b>  Many of the members and flag settings of the <b>NDIS_RECEIVE_FILTER_GLOBAL_PARAMETERS</b> structure are valid if the miniport driver is enabled to use the VMQ or SR-IOV interface. The miniport driver is enabled to use these interfaces through standardized INF keywords. For more information, see <a href="https://msdn.microsoft.com/EF556563-4097-4388-A563-29FC891AC626">Handling SR-IOV, VMQ, and RSS Standardized INF Keywords</a>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-global-parameters">
   OID_RECEIVE_FILTER_GLOBAL_PARAMETERS</a>
 

 


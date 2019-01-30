---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_INFO
title: "_NDIS_RECEIVE_FILTER_INFO" (ntddndis.h)
description: The NDIS_RECEIVE_FILTER_INFO structure contains information about a receive filter that is currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info.htm
tech.root: netvista
ms.assetid: 12029cfd-58d0-4621-8cbc-c07e68db61b8
ms.date: 05/02/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_INFO, NDIS_RECEIVE_FILTER_INFO, NDIS_RECEIVE_FILTER_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_INFO, PNDIS_RECEIVE_FILTER_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_INFO, netvista.ndis_receive_filter_info, ntddndis/NDIS_RECEIVE_FILTER_INFO, ntddndis/PNDIS_RECEIVE_FILTER_INFO, virtual_machine_queue_ref_4c711292-ce17-4eb9-a051-c32f8ad6f49e.xml"
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
-	NDIS_RECEIVE_FILTER_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_INFO, *PNDIS_RECEIVE_FILTER_INFO
---

# _NDIS_RECEIVE_FILTER_INFO structure


## -description



The <b>NDIS_RECEIVE_FILTER_INFO</b> structure contains information about a receive filter that is currently configured on a miniport driver.



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
     <b>NDIS_RECEIVE_FILTER_INFO</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_INFO</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_INFO_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_REVISION_1.


### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.


### -field FilterType

The type of the receive filter.


### -field FilterId

A receive filter identifier. The filter identifier
     is an integer from one up to and including the number of receive filters that the network adapter
     supports. A value of zero is not valid.


## -remarks



The <b>NDIS_RECEIVE_FILTER_INFO</b> structure is used with the 
    <a href="https://msdn.microsoft.com/32896b46-1143-4598-ad15-2eb4dbdea6e8">
    NDIS_RECEIVE_FILTER_INFO_ARRAY</a> structure for the 
    OID request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates receive filters that have been configured on the miniport driver. This includes packet coalescing receive filters or the receive filters configured on a  receive queue that is used in the VMQ or SR-IOV interface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/32896b46-1143-4598-ad15-2eb4dbdea6e8">
   NDIS_RECEIVE_FILTER_INFO_ARRAY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>
 

 


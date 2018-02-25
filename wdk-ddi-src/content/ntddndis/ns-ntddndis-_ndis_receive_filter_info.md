---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_INFO
title: "_NDIS_RECEIVE_FILTER_INFO"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_INFO structure contains information about a receive filter that is currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info.htm
old-project: netvista
ms.assetid: 12029cfd-58d0-4621-8cbc-c07e68db61b8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PNDIS_RECEIVE_FILTER_INFO, ,, C, D, E, F, I, L, N, NDIS_RECEIVE_FILTER_INFO, NDIS_RECEIVE_FILTER_INFO structure [Network Drivers Starting with Windows Vista], O, P, PNDIS_RECEIVE_FILTER_INFO, PNDIS_RECEIVE_FILTER_INFO structure pointer [Network Drivers Starting with Windows Vista], R, S, T, V, _, _NDIS_RECEIVE_FILTER_INFO, netvista.ndis_receive_filter_info, ntddndis/NDIS_RECEIVE_FILTER_INFO, ntddndis/PNDIS_RECEIVE_FILTER_INFO, virtual_machine_queue_ref_4c711292-ce17-4eb9-a051-c32f8ad6f49e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_RECEIVE_FILTER_INFO
product: Windows
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

## -syntax


````
typedef struct _NDIS_RECEIVE_FILTER_INFO {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    Flags;
  NDIS_RECEIVE_FILTER_TYPE FilterType;
  NDIS_RECEIVE_FILTER_ID   FilterId;
} NDIS_RECEIVE_FILTER_INFO, *PNDIS_RECEIVE_FILTER_INFO;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
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
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_info_array.md">
    NDIS_RECEIVE_FILTER_INFO_ARRAY</a> structure for the 
    OID request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates receive filters that have been configured on the miniport driver. This includes packet coalescing receive filters or the receive filters configured on a  receive queue that is used in the VMQ or SR-IOV interface.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_filter_info_array.md">
   NDIS_RECEIVE_FILTER_INFO_ARRAY</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


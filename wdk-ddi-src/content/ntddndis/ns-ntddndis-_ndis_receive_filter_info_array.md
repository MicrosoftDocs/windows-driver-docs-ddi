---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_INFO_ARRAY
title: "_NDIS_RECEIVE_FILTER_INFO_ARRAY"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_INFO_ARRAY structure specifies a list of receive filters that are currently configured on a miniport driver.
old-location: netvista\ndis_receive_filter_info_array.htm
old-project: netvista
ms.assetid: 32896b46-1143-4598-ad15-2eb4dbdea6e8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_INFO_ARRAY, NDIS_RECEIVE_FILTER_INFO_ARRAY, NDIS_RECEIVE_FILTER_INFO_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_INFO_ARRAY, PNDIS_RECEIVE_FILTER_INFO_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_INFO_ARRAY, netvista.ndis_receive_filter_info_array, ntddndis/NDIS_RECEIVE_FILTER_INFO_ARRAY, ntddndis/PNDIS_RECEIVE_FILTER_INFO_ARRAY, virtual_machine_queue_ref_f87d474d-4909-48ed-8891-7213bd4dcbc1.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_RECEIVE_FILTER_INFO_ARRAY
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_INFO_ARRAY, *PNDIS_RECEIVE_FILTER_INFO_ARRAY
---

# _NDIS_RECEIVE_FILTER_INFO_ARRAY structure


## -description



The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure specifies a list of receive filters that are currently configured on a miniport driver.



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

The type, revision, and size of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2

Added members for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_2.



#### NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1

Original version for NDIS 6.20.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_INFO_ARRAY_REVISION_1.


### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Miniport drivers that support <a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS packet coalescing</a> or SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FirstElementOffset

The offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567176">NDIS_RECEIVE_FILTER_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

The number of elements in the array.


### -field ElementSize

The size, in bytes, of each element in the array.


### -field Flags

A  bitwise OR of the following flags: 





#### NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED

If this flag is set, information is requested about receive filters that are configured on the virtual port (VPort) specified by the <b>VPortId</b> member.

<div class="alert"><b>Note</b>  This flag is only valid for the SR-IOV interface.</div>
<div> </div>

### -field VPortId

The virtual port (VPort) identifier on which receive filters are being queried. The VPort identifier must be one of the following values:

<ul>
<li>


The identifier of a VPort that was previously allocated through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.



</li>
<li>
A value of NDIS_DEFAULT_VPORT_ID that specifies the default VPort on the NIC switch.



</li>
</ul>
A NIC switch is supported by network adapters for the SR-IOV interface. The NIC switch can be configured to have one or more VPorts.

<div class="alert"><b>Note</b>  The <b>VPortId</b> member is only valid if the NDIS_RECEIVE_FILTER_INFO_ARRAY_VPORT_ID_SPECIFIED flag is set in <b>Flags</b>. 
</div>
<div> </div>

## -remarks



The <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is used in the 
    OID request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-enum-filters">
    OID_RECEIVE_FILTER_ENUM_FILTERS</a>. This OID request enumerates the receive filters on a VMQ  or SR-IOV receive queue. Each
    element in the array that follows the <b>NDIS_RECEIVE_FILTER_INFO_ARRAY</b> structure is an 
    <a href="https://msdn.microsoft.com/12029cfd-58d0-4621-8cbc-c07e68db61b8">
    NDIS_RECEIVE_FILTER_INFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567176">NDIS_RECEIVE_FILTER_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-enum-filters">OID_RECEIVE_FILTER_ENUM_FILTERS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_INFO_ARRAY structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes

---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
title: "_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure contains information about the allocation status of a batch of receive queues.
old-location: netvista\ndis_receive_queue_allocation_complete_array.htm
tech.root: netvista
ms.assetid: f071569f-fa99-4614-96a7-edf73a85d96a
ms.date: 5/2/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, netvista.ndis_receive_queue_allocation_complete_array, ntddndis/NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, ntddndis/PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, virtual_machine_queue_ref_2b5d6225-cfe9-4ed0-8a4b-02135f4b37c8.xml"
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
-	NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
product:
- Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
---

# _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure


## -description


The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure contains information about the allocation
  status of a batch of receive queues.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="https://msdn.microsoft.com/1aae1bc7-24c6-46a3-be0e-f028d6b70774">
     NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A <b>ULONG</b> value for the number of elements in the list of elements that follow the
     <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure.


### -field ElementSize

A <b>ULONG</b> value that specifies the size, in bytes, of each element in the array.


## -remarks



The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure is used in the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
    OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID.

Each element in the array that follows this structure is an 
    <a href="https://msdn.microsoft.com/1aae1bc7-24c6-46a3-be0e-f028d6b70774">
    NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/1aae1bc7-24c6-46a3-be0e-f028d6b70774">
   NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>
 

 


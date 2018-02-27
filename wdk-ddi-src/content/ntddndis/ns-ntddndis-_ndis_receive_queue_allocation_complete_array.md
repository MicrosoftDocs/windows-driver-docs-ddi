---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
title: "_NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY"
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure contains information about the allocation status of a batch of receive queues.
old-location: netvista\ndis_receive_queue_allocation_complete_array.htm
old-project: netvista
ms.assetid: f071569f-fa99-4614-96a7-edf73a85d96a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, netvista.ndis_receive_queue_allocation_complete_array, ntddndis/NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, ntddndis/PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, virtual_machine_queue_ref_2b5d6225-cfe9-4ed0-8a4b-02135f4b37c8.xml"
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
-	NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY
---

# _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure


## -description


The <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure contains information about the allocation
  status of a batch of receive queues.


## -syntax


````
typedef struct _NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  ULONG              FirstElementOffset;
  ULONG              NumElements;
  ULONG              ElementSize;
} NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY, *PNDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b>  structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_allocation_complete_parameters.md">
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
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
    OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a> OID.

Each element in the array that follows this structure is an 
    <a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_allocation_complete_parameters.md">
    NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</a> structure.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_receive_queue_allocation_complete_parameters.md">
   NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_PARAMETERS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-queue-allocation-complete">
   OID_RECEIVE_FILTER_QUEUE_ALLOCATION_COMPLETE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_ALLOCATION_COMPLETE_ARRAY structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


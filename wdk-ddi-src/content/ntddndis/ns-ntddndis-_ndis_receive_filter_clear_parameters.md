---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
title: "_NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure specifies the parameters to clear a receive filter on a network adapter.
old-location: netvista\ndis_receive_filter_clear_parameters.htm
old-project: netvista
ms.assetid: 101f9fea-cfc2-4ea5-82ee-a260d10b5a96
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, virtual_machine_queue_ref_c0ec4d22-f248-4fe1-855e-99cfe6b2cd1f.xml, PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], *PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, netvista.ndis_receive_filter_clear_parameters, PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure [Network Drivers Starting with Windows Vista], NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
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
-	NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS"
---

# _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure


## -description



The <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure specifies the parameters to clear a
  receive filter on a network adapter. 



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
typedef struct _NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  NDIS_RECEIVE_QUEUE_ID  QueueId;
  NDIS_RECEIVE_FILTER_ID FilterId;
} NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS, *PNDIS_RECEIVE_FILTER_CLEAR_PARAMETERS;
````


## -struct-fields




### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT.

To indicate the version of the <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure, the driver sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS_REVISION_1

Original version for NDIS 6.20.

The driver sets the 
        <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_CLEAR_PARAMETERS_REVISION_1.


### -field Flags

A bitwise OR of flags. This member is reserved for NDIS.


### -field QueueId

A receive queue identifier. This identifier is an
     integer between zero and the number of queues that the network adapter supports. A value of NDIS_DEFAULT_RECEIVE_QUEUE_ID specifies
     the default receive queue.

<div class="alert"><b>Note</b>  Miniport drivers that support <a href="https://msdn.microsoft.com/500FBF0F-54D9-4675-8E2D-447387DA8798">NDIS packet coalescing</a> or the SR-IOV interface must set the <b>QueueId</b> member to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>

### -field FilterId

A receive filter identifier. The filter identifier
     is an integer from one to the number of receive filters that the network adapter supports. A value of zero is
     not valid.


## -remarks



The <b>NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS</b> structure is used with OID requests of   
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569785">OID_RECEIVE_FILTER_CLEAR_FILTER</a> to specify a filter to clear on a VMQ or SR-IOV VPort receive queue. The filter was
    previously set on the queue with the 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">
    OID_RECEIVE_FILTER_SET_FILTER</a> OID.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569785">OID_RECEIVE_FILTER_CLEAR_FILTER</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_CLEAR_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


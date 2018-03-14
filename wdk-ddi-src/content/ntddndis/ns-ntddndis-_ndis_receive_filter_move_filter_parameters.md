---
UID: NS:ntddndis._NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS
title: "_NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS"
author: windows-driver-content
description: The NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure specifies the parameters for moving a previously created receive filter. A receive filter is moved from a receive queue on a virtual port (VPort) to a receive queue on another VPort.
old-location: netvista\ndis_receive_filter_move_filter_parameters.htm
old-project: netvista
ms.assetid: 4045d8ed-bf8d-4dc1-80c3-a77499a7bf4e
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, netvista.ndis_receive_filter_move_filter_parameters, ntddndis/NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, ntddndis/PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
-	NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, *PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS
---

# _NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure


## -description


The <b>NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS</b> structure specifies the parameters for moving a previously created receive filter. A receive filter is moved  from a receive queue on a virtual port (VPort) to a receive queue on another VPort.


## -syntax


````
typedef struct _NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS {
  NDIS_OBJECT_HEADER       Header;
  NDIS_RECEIVE_FILTER_ID   FilterId;
  NDIS_RECEIVE_QUEUE_ID    SourceQueueId;
  NDIS_NIC_SWITCH_VPORT_ID SourceVPortId;
  NDIS_RECEIVE_QUEUE_ID    DestQueueId;
  NDIS_NIC_SWITCH_VPORT_ID DestVPortId;
} NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS, *PNDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS;
````


## -struct-fields




### -field Header

The type, revision, and size of the <b>NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS_REVISION_1.


### -field FilterId

An NDIS_RECEIVE_FILTER_ID value that  specifies the identifier of the receive filter.

<div class="alert"><b>Note</b>   The filter specified by this value must have been previously set through an OID method request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>.</div>
<div> </div>

### -field SourceQueueId

An NDIS_RECEIVE_QUEUE_ID value that specifies the identifier of the receive queue on which this filter was previously set. For more information, see the Remarks section.


### -field SourceVPortId

An NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier of the VPort on which this filter was previously set.


### -field DestQueueId

An NDIS_RECEIVE_QUEUE_ID value that specifies the identifier of the receive queue on which the filter is to be moved. For more information, see the Remarks section.


### -field DestVPortId

An NDIS_NIC_SWITCH_VPORT_ID value that specifies the identifier of the VPort on which this filter is to be moved.


## -remarks



This structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451845">OID_RECEIVE_FILTER_MOVE_FILTER</a>.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, the single root I/O virtualization (SR-IOV) interface allows receive filters to be set only  on the default receive queue on both default and nondefault VPorts. The <b>SourceQueueId</b> and <b>DestQueueId</b> members must always be set to NDIS_DEFAULT_RECEIVE_QUEUE_ID.</div>
<div> </div>



## -see-also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451845">OID_RECEIVE_FILTER_MOVE_FILTER</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_FILTER_MOVE_FILTER_PARAMETERS structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NS:ntddndis._NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
title: _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
author: windows-driver-content
description: The NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure identifies a receive queue to free.
old-location: netvista\ndis_receive_queue_free_parameters.htm
old-project: netvista
ms.assetid: b67e7929-e6b3-4d0b-aff9-943a7fbae8ee
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS, NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
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
req.alt-api: NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
req.alt-loc: Ntddndis.h
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
req.typenames: *PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS, NDIS_RECEIVE_QUEUE_FREE_PARAMETERS
---

# _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure



## -description
The <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure identifies a receive queue to free.



## -syntax

````
typedef struct _NDIS_RECEIVE_QUEUE_FREE_PARAMETERS {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 Flags;
  NDIS_RECEIVE_QUEUE_ID QueueId;
} NDIS_RECEIVE_QUEUE_FREE_PARAMETERS, *PNDIS_RECEIVE_QUEUE_FREE_PARAMETERS;
````


## -struct-fields

### -field Header

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure. The driver sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to<b> NDIS_RECEIVE_QUEUE_FREE_PARAMETERS_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_RECEIVE_QUEUE_FREE_PARAMETERS_REVISION_1</b>.


### -field Flags

A <b>ULONG</b> value that contains a bitwise <b>OR</b> of flags. This member is reserved for NDIS.


### -field QueueId

An <b>NDIS_RECEIVE_QUEUE_ID</b> type value that contains a receive queue identifier. This identifier is an
     integer value between one and the number of queues that the network adapter supports. 

<div class="alert"><b>Note</b>  The default receive queue is always allocated and can never be freed. Drivers must not set the <b>QueueId</b> member to  <b>NDIS_DEFAULT_RECEIVE_QUEUE_ID</b>.</div>
<div> </div>

## -remarks
The <b>NDIS_RECEIVE_QUEUE_FREE_PARAMETERS</b> structure is used in the 
    <a href="netvista.oid_receive_filter_free_queue">
    OID_RECEIVE_FILTER_FREE_QUEUE</a> OID.


## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569789">OID_RECEIVE_FILTER_FREE_QUEUE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RECEIVE_QUEUE_FREE_PARAMETERS structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


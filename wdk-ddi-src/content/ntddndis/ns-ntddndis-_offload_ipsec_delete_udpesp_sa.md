---
UID: NS:ntddndis._OFFLOAD_IPSEC_DELETE_UDPESP_SA
title: _OFFLOAD_IPSEC_DELETE_UDPESP_SA
author: windows-driver-content
description: The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA) and parser entry that a miniport driver deletes from a NIC.
old-location: netvista\offload_ipsec_delete_udpesp_sa.htm
old-project: netvista
ms.assetid: f1304fb4-87c8-4a0f-a10f-6a2c5cbaed20
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _OFFLOAD_IPSEC_DELETE_UDPESP_SA, OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OFFLOAD_IPSEC_DELETE_UDPESP_SA
req.alt-loc: ntddndis.h
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
req.typenames: OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA
---

# _OFFLOAD_IPSEC_DELETE_UDPESP_SA structure



## -description
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure contains information for each security association (SA)
  and parser entry that a miniport driver deletes from a NIC.



## -syntax

````
typedef struct _OFFLOAD_IPSEC_DELETE_UDPESP_SA {
  HANDLE OffloadHandle;
  HANDLE EncapTypeEntryOffldHandle;
} OFFLOAD_IPSEC_DELETE_UDPESP_SA, *POFFLOAD_IPSEC_DELETE_UDPESP_SA;
````


## -struct-fields

### -field OffloadHandle

The handle for the SA to be deleted.


### -field EncapTypeEntryOffldHandle

When <b>NULL</b>, the miniport does not have to delete a parser entry in addition to the specified SA.
     When non-<b>NULL</b>, this member specifies the handle for the parser entry to be deleted.


## -remarks
The OFFLOAD_IPSEC_DELETE_UDPESP_SA structure is used with the 
    <a href="netvista.oid_tcp_task_ipsec_delete_udpesp_sa">
    OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a> OID.


## -see-also
<dl>
<dt>
<a href="netvista.oid_tcp_task_ipsec_delete_udpesp_sa">
   OID_TCP_TASK_IPSEC_DELETE_UDPESP_SA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20OFFLOAD_IPSEC_DELETE_UDPESP_SA structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


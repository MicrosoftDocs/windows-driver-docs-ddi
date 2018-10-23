---
UID: NS:ndis._IPSEC_OFFLOAD_V2_DELETE_SA
title: "_IPSEC_OFFLOAD_V2_DELETE_SA"
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_DELETE_SA structure specifies a security association (SA) that should be deleted from a NIC and a pointer to the next IPSEC_OFFLOAD_V2_DELETE_SA structure in a linked list.
old-location: netvista\ipsec_offload_v2_delete_sa.htm
tech.root: netvista
ms.assetid: a75088e8-c7a5-4ca4-a8fc-8e88f9e20bb9
ms.date: 05/02/2018
ms.keywords: "*PIPSEC_OFFLOAD_V2_DELETE_SA, IPSEC_OFFLOAD_V2_DELETE_SA, IPSEC_OFFLOAD_V2_DELETE_SA structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_DELETE_SA, PIPSEC_OFFLOAD_V2_DELETE_SA structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_DELETE_SA, ndis/IPSEC_OFFLOAD_V2_DELETE_SA, ndis/PIPSEC_OFFLOAD_V2_DELETE_SA, netvista.ipsec_offload_v2_delete_sa, task_offload_IPsecv2_ref_98d355a4-b502-4601-a419-815d4de90c6f.xml"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	ndis.h
api_name:
-	IPSEC_OFFLOAD_V2_DELETE_SA
product:
- Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_DELETE_SA, *PIPSEC_OFFLOAD_V2_DELETE_SA
---

# _IPSEC_OFFLOAD_V2_DELETE_SA structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_DELETE_SA structure specifies a security association (SA) that should be deleted
  from a NIC and a pointer to the next IPSEC_OFFLOAD_V2_DELETE_SA structure in a linked list.


## -struct-fields




### -field Header

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     IPSEC_OFFLOAD_V2_DELETE_SA structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_DEFAULT, the 
     <b>Revision</b> member to NDIS_IPSEC_OFFLOAD_V2_DELETE_SA_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_IPSEC_OFFLOAD_V2_DELETE_SA_REVISION_1.


### -field Next

A pointer to an IPSEC_OFFLOAD_V2_DELETE_SA structure that is the next structure in a linked list.
     If the pointer is <b>NULL</b>, the current structure is the last structure in the list.


### -field OffloadHandle

An NDIS handle that identifies the SA. The miniport driver provided this handle in response to an 
      OID set request of <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>.


## -remarks



The IPSEC_OFFLOAD_V2_DELETE_SA structure defines a handle for a SA that should be deleted and a
    pointer to the next IPSEC_OFFLOAD_V2_DELETE_SA structure in a linked list. The IPSEC_OFFLOAD_V2_DELETE_SA
    structure is used with the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
    OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a> OID.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-add-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/oid-tcp-task-ipsec-offload-v2-delete-sa">
   OID_TCP_TASK_IPSEC_OFFLOAD_V2_DELETE_SA</a>
 

 


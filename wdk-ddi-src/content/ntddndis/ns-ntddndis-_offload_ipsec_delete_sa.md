---
UID: NS:ntddndis._OFFLOAD_IPSEC_DELETE_SA
title: "_OFFLOAD_IPSEC_DELETE_SA"
description: The OFFLOAD_IPSEC_DELETE_SA structure contains information for each security association (SA) that a miniport driver deletes from a NIC.
old-location: netvista\offload_ipsec_delete_sa.htm
tech.root: netvista
ms.assetid: a8c34bf8-1f3a-4aa3-834b-5824402bd88c
ms.date: 05/02/2018
ms.keywords: "*POFFLOAD_IPSEC_DELETE_SA, 216offload_1e6bbc64-755a-4da3-a7d2-ce57c4b98ce6.xml, OFFLOAD_IPSEC_DELETE_SA, OFFLOAD_IPSEC_DELETE_SA structure [Network Drivers Starting with Windows Vista], POFFLOAD_IPSEC_DELETE_SA, POFFLOAD_IPSEC_DELETE_SA structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_IPSEC_DELETE_SA, netvista.offload_ipsec_delete_sa, ntddndis/OFFLOAD_IPSEC_DELETE_SA, ntddndis/POFFLOAD_IPSEC_DELETE_SA"
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	ntddndis.h
api_name:
-	OFFLOAD_IPSEC_DELETE_SA
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_IPSEC_DELETE_SA, *POFFLOAD_IPSEC_DELETE_SA
---

# _OFFLOAD_IPSEC_DELETE_SA structure


## -description


The OFFLOAD_IPSEC_DELETE_SA structure contains information for each security association (SA) that a
  miniport driver deletes from a NIC.


## -struct-fields




### -field OffloadHandle

The handle for the SA to be deleted.


## -remarks



The OFFLOAD_IPSEC_DELETE_SA structure is used with the 
    <a href="https://msdn.microsoft.com/library/gg155485.aspx">
    OID_TCP_TASK_IPSEC_DELETE_SA</a> OID.




## -see-also




<a href="https://msdn.microsoft.com/library/gg155485.aspx">OID_TCP_TASK_IPSEC_DELETE_SA</a>
 

 


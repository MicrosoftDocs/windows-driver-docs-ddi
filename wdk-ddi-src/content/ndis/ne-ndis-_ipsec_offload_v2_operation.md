---
UID: NE:ndis._IPSEC_OFFLOAD_V2_OPERATION
title: _IPSEC_OFFLOAD_V2_OPERATION (ndis.h)
description: The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security association (SA) is used.
old-location: netvista\ipsec_offload_v2_operation.htm
tech.root: netvista
ms.assetid: bb26c8af-1564-4cf8-ab40-b50b4811466d
ms.date: 05/02/2018
keywords: ["_IPSEC_OFFLOAD_V2_OPERATION enumeration"]
ms.keywords: "*PIPSEC_OFFLOAD_V2_OPERATION, IPSEC_OFFLOAD_V2_OPERATION, IPSEC_OFFLOAD_V2_OPERATION enumeration [Network Drivers Starting with Windows Vista], IPsecOffloadV2Ah, IPsecOffloadV2Esp, IPsecOffloadV2Max, PIPSEC_OFFLOAD_V2_OPERATION, PIPSEC_OFFLOAD_V2_OPERATION enumeration pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_OPERATION, ndis/IPSEC_OFFLOAD_V2_OPERATION, ndis/IPsecOffloadV2Ah, ndis/IPsecOffloadV2Esp, ndis/IPsecOffloadV2Max, ndis/PIPSEC_OFFLOAD_V2_OPERATION, netvista.ipsec_offload_v2_operation, task_offload_IPsecv2_ref_37a1424a-fe40-440d-a071-9483c5bcb516.xml"
f1_keywords:
 - "ndis/IPSEC_OFFLOAD_V2_OPERATION"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ndis.h
api_name:
- IPSEC_OFFLOAD_V2_OPERATION
product:
- Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_OPERATION, *PIPSEC_OFFLOAD_V2_OPERATION
---

# _IPSEC_OFFLOAD_V2_OPERATION enumeration


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the IPsec operation for which a security
  association (SA) is used.


## -enum-fields




### -field IPsecOffloadV2Ah

The SA is used for authentication (integrity checking).


### -field IPsecOffloadV2Esp

The SA is used for encryption/decryption (confidentiality).


### -field IPsecOffloadV2Max

Reserved for NDIS.


## -remarks



The IPSEC_OFFLOAD_V2_OPERATION enumeration specifies the operation for which an SA is used in the 
    <b>Operation</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ipsec_offload_v2_security_association">
    IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ipsec_offload_v2_security_association">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>
 

 


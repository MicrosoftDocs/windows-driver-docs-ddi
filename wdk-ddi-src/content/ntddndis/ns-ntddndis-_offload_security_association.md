---
UID: NS:ntddndis._OFFLOAD_SECURITY_ASSOCIATION
title: _OFFLOAD_SECURITY_ASSOCIATION (ntddndis.h)
description: The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\offload_security_association.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["OFFLOAD_SECURITY_ASSOCIATION structure"]
ms.keywords: "*POFFLOAD_SECURITY_ASSOCIATION, 216offload_3c6a958b-81b2-4f18-b974-b0669b6294e1.xml, OFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION structure [Network Drivers Starting with Windows Vista], POFFLOAD_SECURITY_ASSOCIATION, POFFLOAD_SECURITY_ASSOCIATION structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_SECURITY_ASSOCIATION, netvista.offload_security_association, ntddndis/OFFLOAD_SECURITY_ASSOCIATION, ntddndis/POFFLOAD_SECURITY_ASSOCIATION"
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
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
f1_keywords:
 - _OFFLOAD_SECURITY_ASSOCIATION
 - ntddndis/_OFFLOAD_SECURITY_ASSOCIATION
 - POFFLOAD_SECURITY_ASSOCIATION
 - ntddndis/POFFLOAD_SECURITY_ASSOCIATION
 - OFFLOAD_SECURITY_ASSOCIATION
 - ntddndis/OFFLOAD_SECURITY_ASSOCIATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - _OFFLOAD_SECURITY_ASSOCIATION
 - POFFLOAD_SECURITY_ASSOCIATION
 - OFFLOAD_SECURITY_ASSOCIATION
---

# _OFFLOAD_SECURITY_ASSOCIATION structure


## -description

The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).

## -struct-fields

### -field Operation

The Internet Protocol security (IPsec) operation for which the SA is to be used. The following
     operations are supported:
     





#### AUTHENTICATE

The SA will be used for authentication (integrity checking).



#### ENCRYPT

The SA will be used for encryption/decryption (confidentiality).

### -field SPI

The Security Parameters Index (SPI) for the SA.

### -field IntegrityAlgo

The integrity (authentication) algorithm for the SA, formatted as an 
     <a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_offload_algo_info">OFFLOAD_ALGO_INFO</a> structure.

### -field ConfAlgo

The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     OFFLOAD_ALGO_INFO structure.

### -field Reserved

This member is reserved.

## -remarks

The OFFLOAD_SECURITY_ASSOCIATION structure is used with the 
    <a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-sa">OID_TCP_TASK_IPSEC_ADD_SA</a> and 
    <a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
    OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a> OIDs.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddndis/ns-ntddndis-_offload_algo_info">OFFLOAD_ALGO_INFO</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-sa">OID_TCP_TASK_IPSEC_ADD_SA</a>



<a href="/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
   OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a>


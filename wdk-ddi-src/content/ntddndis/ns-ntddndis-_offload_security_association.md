---
UID: NS:ntddndis._OFFLOAD_SECURITY_ASSOCIATION
title: "_OFFLOAD_SECURITY_ASSOCIATION"
author: windows-driver-content
description: The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\offload_security_association.htm
old-project: netvista
ms.assetid: 2c392a13-4db4-4b22-aacf-4450eb1e191c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*POFFLOAD_SECURITY_ASSOCIATION, 216offload_3c6a958b-81b2-4f18-b974-b0669b6294e1.xml, OFFLOAD_SECURITY_ASSOCIATION, OFFLOAD_SECURITY_ASSOCIATION structure [Network Drivers Starting with Windows Vista], POFFLOAD_SECURITY_ASSOCIATION, POFFLOAD_SECURITY_ASSOCIATION structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_SECURITY_ASSOCIATION, netvista.offload_security_association, ntddndis/OFFLOAD_SECURITY_ASSOCIATION, ntddndis/POFFLOAD_SECURITY_ASSOCIATION"
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
-	ntddndis.h
api_name:
-	OFFLOAD_SECURITY_ASSOCIATION
product: Windows
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
---

# _OFFLOAD_SECURITY_ASSOCIATION structure


## -description


The OFFLOAD_SECURITY_ASSOCIATION structure specifies a single security association (SA).


## -syntax


````
typedef struct _OFFLOAD_SECURITY_ASSOCIATION {
  OFFLOAD_OPERATION_E Operation;
  SPI_TYPE            SPI;
  OFFLOAD_ALGO_INFO   IntegrityAlgo;
  OFFLOAD_ALGO_INFO   ConfAlgo;
  OFFLOAD_ALGO_INFO   Reserved;
} OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION;
````


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
     <a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a> structure.


### -field ConfAlgo

The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     OFFLOAD_ALGO_INFO structure.


### -field Reserved

This member is reserved.


## -remarks



The OFFLOAD_SECURITY_ASSOCIATION structure is used with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a> and 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
    OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a> OIDs.




## -see-also

<a href="..\ntddndis\ns-ntddndis-_offload_algo_info.md">OFFLOAD_ALGO_INFO</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-tcp-task-ipsec-add-udpesp-sa">
   OID_TCP_TASK_IPSEC_ADD_UDPESP_SA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569808">OID_TCP_TASK_IPSEC_ADD_SA</a>



 

 



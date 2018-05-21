---
UID: NS:ndis._IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
title: "_IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION"
author: windows-driver-content
description: The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure specifies a single security association (SA).
old-location: netvista\ipsec_offload_v2_security_association.htm
old-project: netvista
ms.assetid: b2c5611e-930d-41a5-a07e-7de8f8584283
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, ndis/IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, ndis/PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, netvista.ipsec_offload_v2_security_association, task_offload_IPsecv2_ref_ccf0a55c-3609-4e15-928a-e46113b96df0.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
product:
- Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, *PIPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION
---

# _IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure specifies a single security association
  (SA).


## -struct-fields




### -field Flags

A set of flags that can be combined with a bitwise OR operation. Otherwise, set this member to
     zero. The following values are valid:
     





#### IPSEC_OFFLOAD_V2_ESN_SA

Specifies ESN SA.


### -field Operation

The IPsec operation for which the SA is to be used. The 
     <a href="https://msdn.microsoft.com/bb26c8af-1564-4cf8-ab40-b50b4811466d">
     IPSEC_OFFLOAD_V2_OPERATION</a> enumeration defines the supported operations.


### -field Spi

A 32 bit security parameters index (SPI) for the SA.


### -field AuthenticationAlgorithm

The integrity (authentication) algorithm for the SA, formatted as an 
     <a href="https://msdn.microsoft.com/787e5a98-ba77-42d4-8624-abcc02fccf53">
     IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a> structure.


### -field EncryptionAlgorithm

The confidentiality (encryption/decryption) algorithm for the SA, formatted as an
     IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure. 
     

<div class="alert"><b>Note</b>  For AES-GCM, the 
     <b>EncryptionAlgorithm</b> member contains the key information. The 
     <b>AuthenticationAlgorithm</b> member of IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, and the key length and
     offset in IPSEC_OFFLOAD_V2_ALGORITHM_INFO, should not be used.</div>
<div> </div>

### -field SequenceNumberHighOrder

The sequence number high-order extension. This sequence number high-order extension is defined in
     RFC 4304. This member represents the high-order portion of the sequence number that is not included in
     the IPsec header.


## -remarks



The IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure is an element in the 
    <b>SecAssoc</b> variable-length array in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a> structure.
    The number of SAs in the IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION structure is specified in the 
    <b>NumExtHdrs</b> member of IPSEC_OFFLOAD_V2_ADD_SA.

A 
    <b>SecAssoc</b> element that is specified for use in processing authentication headers (AH) will have an
    operation type (the 
    <b>Operation</b> member) of 
    <b>IPsecOffloadV2Ah</b> and will have the authentication algorithm in the 
    <b>AuthenticationAlgorithm</b> member. The SA will not have an encryption algorithm in the 
    <b>EncryptionAlgorithm</b> member, so 
    <b>EncryptionAlgorithm</b> will contain zeros.

<div class="alert"><b>Note</b>  For AES-GCM, the 
    <b>EncryptionAlgorithm</b> member contains the key information. The 
    <b>AuthenticationAlgorithm</b> member of IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, and the key length and
    offset in IPSEC_OFFLOAD_V2_ALGORITHM_INFO, should not be used.</div>
<div> </div>
A 
    <b>SecAssoc</b> element that is specified for use in processing encapsulating security payloads (ESPs)
    will have an operation type (the 
    <b>Operation</b> member) of 
    <b>IPsecOffloadV2Esp</b> and can have an authentication algorithm, an encryption algorithm, or both. Note
    that for combined mode algorithms, only the 
    <b>EncryptionAlgorithm</b> member will be specified.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://msdn.microsoft.com/787e5a98-ba77-42d4-8624-abcc02fccf53">
   IPSEC_OFFLOAD_V2_ALGORITHM_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556984">IPSEC_OFFLOAD_V2_OPERATION</a>
 

 


---
UID: NS:ndis._IPSEC_OFFLOAD_V2_ALGORITHM_INFO
title: "_IPSEC_OFFLOAD_V2_ALGORITHM_INFO" (ndis.h)
description: The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies an algorithm that is used for a security association (SA).
old-location: netvista\ipsec_offload_v2_algorithm_info.htm
tech.root: netvista
ms.assetid: 787e5a98-ba77-42d4-8624-abcc02fccf53
ms.date: 05/02/2018
ms.keywords: "*PIPSEC_OFFLOAD_V2_ALGORITHM_INFO, IPSEC_OFFLOAD_V2_ALGORITHM_INFO, IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure [Network Drivers Starting with Windows Vista], PIPSEC_OFFLOAD_V2_ALGORITHM_INFO, PIPSEC_OFFLOAD_V2_ALGORITHM_INFO structure pointer [Network Drivers Starting with Windows Vista], _IPSEC_OFFLOAD_V2_ALGORITHM_INFO, ndis/IPSEC_OFFLOAD_V2_ALGORITHM_INFO, ndis/PIPSEC_OFFLOAD_V2_ALGORITHM_INFO, netvista.ipsec_offload_v2_algorithm_info, task_offload_IPsecv2_ref_72dc6155-8044-4b56-b7c7-0587bf82889d.xml"
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
-	IPSEC_OFFLOAD_V2_ALGORITHM_INFO
product:
- Windows
targetos: Windows
req.typenames: IPSEC_OFFLOAD_V2_ALGORITHM_INFO, *PIPSEC_OFFLOAD_V2_ALGORITHM_INFO
---

# _IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies an algorithm that is used for a security
  association (SA).


## -struct-fields




### -field Identifier

The encryption or authentication algorithm that is used for the SA. 
     

If the algorithm is an encryption algorithm, 
     <b>Identifier</b> can be any of the following values:





#### IPSEC_OFFLOAD_V2_ENCRYPTION_NONE

Specifies no confidentiality algorithm. This value is used for null encryption--that is, when a
       packet is not encrypted but does include ESP authentication information.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_DES_CBC

Specifies the DES algorithm for encrypting and decrypting ESP payloads.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_3_DES_CBC

Specifies the triple-DES algorithm for encrypting and decrypting ESP payloads.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_128

Specifies the AES-GCM 128 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_192

Specifies the AES-GCM 192 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_GCM_256

Specifies the AES-GCM 256 algorithm for encrypting and computing a cryptographic checksum or
       decrypting and validating a cryptographic checksum for an ESP payload. Note that this is a combined
       mode algorithm.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_128

Specifies the Advanced Encryption Standard - cipher-block chaining mode (AES-CBC) 128 algorithm
       for encrypting and decrypting ESP payloads.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_192

Specifies the AES-CBC 192 algorithm for encrypting and decrypting ESP payloads.



#### IPSEC_OFFLOAD_V2_ENCRYPTION_AES_CBC_256

Specifies the AES-CBC 256 algorithm for encrypting and decrypting ESP payloads.

If the algorithm is an authentication algorithm, 
     <b>Identifier</b> can be one of the following values:





#### IPSEC_OFFLOAD_V2_AUTHENTICATION_MD5

Specifies the keyed message digest 5 (MD5) algorithm for computing or validating a cryptographic
       checksum.



#### IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_1

Specifies the secure hash algorithm (SHA) 1 algorithm for computing or validating a
       cryptographic checksum.



#### IPSEC_OFFLOAD_V2_AUTHENTICATION_SHA_256

Specifies the SHA 256 algorithm for computing or validating a cryptographic checksum.



#### IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_128

Specifies the Advanced Encryption Standard - Galois/Counter Mode (AES- GMAC) 128 algorithm for
       computing or validating a cryptographic checksum.



#### IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_192

Specifies the AES- GMAC 192 algorithm for computing or validating a cryptographic
       checksum.



#### IPSEC_OFFLOAD_V2_AUTHENTICATION_AES_GCM_256

Specifies the AES- GMAC 256 algorithm for computing or validating a cryptographic
       checksum.


### -field KeyLength

The length, in bytes, of the key for the algorithm. The key is contained in the array at the 
     <b>KeyData</b> member in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a> structure.
     

<b>KeyLength</b> indicates the length of the cryptographic algorithm, starting at the offset that is
     specified in 
     <b>KeyOffsetBytes</b> .

If both algorithms (
     <b>AuthenticationAlgorithm</b> and 
     <b>EncryptionAlgorithm</b> ) are specified in IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION, the keys are
     concatenated. The respective keys start at the offset that is specified in 
     <b>KeyOffsetBytes</b> .


### -field KeyOffsetBytes

The offset, in bytes, into in the array at the 
     <b>KeyData</b> member in the 
     <a href="https://msdn.microsoft.com/78c5e765-40e5-47f0-8460-a86124fb43d8">
     IPSEC_OFFLOAD_V2_ADD_SA</a> structure.


### -field AdditionalInfo

Additional information that should be interpreted differently based on the algorithm. For AES-GCM,     
     <b>AdditionalInfo</b> contains the ICV length.


## -remarks



The IPSEC_OFFLOAD_V2_ALGORITHM_INFO structure specifies algorithm information in the 
    <b>EncryptionAlgorithm</b> and 
    <b>AuthenticationAlgorithm</b> members of the 
    <a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
    IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556977">IPSEC_OFFLOAD_V2_ADD_SA</a>



<a href="https://msdn.microsoft.com/b2c5611e-930d-41a5-a07e-7de8f8584283">
   IPSEC_OFFLOAD_V2_SECURITY_ASSOCIATION</a>
 

 


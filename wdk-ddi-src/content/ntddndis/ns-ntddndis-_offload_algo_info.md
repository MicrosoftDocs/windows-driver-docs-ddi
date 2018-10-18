---
UID: NS:ntddndis._OFFLOAD_ALGO_INFO
title: "_OFFLOAD_ALGO_INFO"
author: windows-driver-content
description: The OFFLOAD_ALGO_INFO structure specifies an algorithm used for a security association (SA).
old-location: netvista\offload_algo_info.htm
tech.root: netvista
ms.assetid: 119a8c88-f181-40f5-8a12-5d663c5a1534
ms.date: 5/2/2018
ms.keywords: "*POFFLOAD_ALGO_INFO, 216offload_d10cb479-3fe8-468d-925b-c8358d88ef2b.xml, OFFLOAD_ALGO_INFO, OFFLOAD_ALGO_INFO structure [Network Drivers Starting with Windows Vista], POFFLOAD_ALGO_INFO, POFFLOAD_ALGO_INFO structure pointer [Network Drivers Starting with Windows Vista], _OFFLOAD_ALGO_INFO, netvista.offload_algo_info, ntddndis/OFFLOAD_ALGO_INFO, ntddndis/POFFLOAD_ALGO_INFO"
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
-	OFFLOAD_ALGO_INFO
product:
- Windows
targetos: Windows
req.typenames: OFFLOAD_ALGO_INFO, *POFFLOAD_ALGO_INFO
---

# _OFFLOAD_ALGO_INFO structure


## -description


The OFFLOAD_ALGO_INFO structure specifies an algorithm used for a security association (SA).


## -struct-fields




### -field algoIdentifier

The confidentiality or integrity algorithm used for the SA. 
     

If the algorithm is a confidentiality algorithm (that is, if the OFFLOAD_ALGO_INFO structure is
     specifying a 
     <b>ConfAlgo</b>), 
     <b>algoIdentifier</b> can be any of the following values:





#### OFFLOAD_IPSEC_CONF_NONE

Specifies no confidentiality algorithm. Used for null encryption--that is, when a packet is not
       encrypted but its ESP header contains authentication information.



#### OFFLOAD_IPSEC_CONF_DES

Specifies the DES algorithm.



#### OFFLOAD_IPSEC_CONF_3_DES

Specifies the triple-DES algorithm.

If the algorithm is an integrity algorithm (that is, if the OFFLOAD_ALGO_INFO structure is specifying
     an 
     <b>IntegrityAlgo</b>), 
     <b>algoIdentifier</b> can be one of the following values:





#### OFFLOAD_IPSEC_INTEGRITY_NONE

Specifies no integrity algorithm. Used when the ESP header contains no authentication
       information.



#### OFFLOAD_IPSEC_INTEGRITY_MD5

Specifies the keyed MD5 algorithm.



#### OFFLOAD_IPSEC_INTEGRITY_SHA

Specifies the SHA 1 algorithm.


### -field algoKeylen

The length, in bytes, of the key for the algorithm. The key is contained in the buffer at 
     <b>KeyMat</b>Â¸ which is the variable-length array specified in the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569056">OFFLOAD_IPSEC_ADD_SA</a> structure.
     

If only an integrity algorithm (
     <b>IntegrityAlgo</b>) is specified in the 
     <a href="https://msdn.microsoft.com/2c392a13-4db4-4b22-aacf-4450eb1e191c">
     OFFLOAD_SECURITY_ASSOCIATION</a> structure, 
     <b>algoKeylen</b> indicates the length of the key for the integrity algorithm,
     starting from the beginning of the buffer at 
     <b>KeyMat</b>.

If both an integrity and a confidentiality algorithm (
     <b>IntegrityAlgo</b> and 
     <b>ConfAlgo</b>) are specified, 
     <b>algoKeylen</b> for the integrity algorithm indicates the length of the key for
     the integrity algorithm, starting from the beginning of the buffer at 
     <b>KeyMat</b>. The 
     <b>algoKeylen</b> for the confidentiality algorithm, in this case, indicates the
     length of the key for the confidentiality algorithm, starting the from the end of the key for the
     integrity algorithm.


### -field algoRounds

The number of transformation rounds that the encryption algorithm performs.

<div class="alert"><b>Note</b>  This member is only used for 
      <a href="https://msdn.microsoft.com/1cf6306c-bb1d-40f6-a0e3-59c14a60a8ff">IPsec Offload Version 1</a>.</div>
<div> </div>

## -remarks



The OFFLOAD_ALGO_INFO structure specifies algorithm information in the 
    <b>IntegrityAlgo</b>, 
    <b>ConfAlgo</b>, and 
    <b>Reserved</b> members of the 
    <a href="https://msdn.microsoft.com/2c392a13-4db4-4b22-aacf-4450eb1e191c">
    OFFLOAD_SECURITY_ASSOCIATION</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569056">OFFLOAD_IPSEC_ADD_SA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569061">OFFLOAD_SECURITY_ASSOCIATION</a>
 

 


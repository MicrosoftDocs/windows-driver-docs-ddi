---
UID: NS:wwan._WWAN_PCO_VALUE
title: "_WWAN_PCO_VALUE"
author: windows-driver-content
description: The WWAN_PCO_VALUE structure represents the PCO information payload from the network as defined in the 3GPP TS24.008 spec.
old-location: netvista\wwan_pco_value.htm
old-project: netvista
ms.assetid: 45A499CE-2C9A-4070-BEF8-880E7673FA8E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_PCO_VALUE, PWWAN_PCO_VALUE, PWWAN_PCO_VALUE structure pointer [Network Drivers Starting with Windows Vista], WWAN_PCO_VALUE, WWAN_PCO_VALUE structure [Network Drivers Starting with Windows Vista], _WWAN_PCO_VALUE, netvista.wwan_pco_value, wwan/PWWAN_PCO_VALUE, wwan/WWAN_PCO_VALUE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	wwan.h
api_name:
-	WWAN_PCO_VALUE
product: Windows
targetos: Windows
req.typenames: WWAN_PCO_VALUE, *PWWAN_PCO_VALUE
req.product: Windows 10 or later.
---

# _WWAN_PCO_VALUE structure


## -description


The <b>WWAN_PCO_VALUE</b> structure represents the PCO information payload from the network as defined in the 3GPP TS24.008 spec.


## -syntax


````
typedef struct _WWAN_PCO_VALUE {
  ULONG         Size;
  WWAN_PCO_TYPE Type;
  BYTE          PcoData[WWAN_PCO_OCT_BUF_LEN];
} WWAN_PCO_VALUE, *PWWAN_PCO_VALUE;
````


## -struct-fields




### -field Size

The length of the PCO value that is valid in <b>PcoData</b>, which will be octets 3 (octet 1 to 3) + m*protocol element length + n*container element length. This is defined in the 3GPP TS24.008 spec, Section 10.5, since PCO is Type 4 information. 


### -field Type

Indicates whether the PCO value being passed up is the original structure that was received by the modem or a subset of the full PCO structure and has the header synthesized. For more info, see <a href="..\wwan\ne-wwan-_wwan_pco_type.md">WWAN_PCO_TYPE</a>.


### -field PcoData

 




#### - PcoData[WWAN_PCO_OCT_BUF_LEN]

The payload of the PCO structure that is received from the operator. The modem should surface the PCO with the complete structure as specified by the 3G TS24.008 spec. <i>WWAN_PCO_HEX_BUF_LEN</i> is defined as <i>256</i>, given that the longest a PCO structure could be is 253 octets.


## -remarks



Because some modems can currently only pass up operator specific PCO elements, the modem should pass up the information following the structure defined by 3GPP TS24.008 with the accurate synthesized header values for the content that is being passed up to the host.

For example, if the modem received a PCO with 3 protocols and 3 containers, and is only passing up the 2 operator specific element containers to the host, the modem will make changes to the header that indicates the length of the PCO structure. This is to reflect the fact that there are only the two containers by subtracting the length of the 3 protocols.

The following figure shows  	a full PCO structure as defined in the 3G TS24.008 spec.

<img alt="Full PCO structure" src="images/pco_structure_small.png"/>



## -see-also

<a href="..\wwan\ne-wwan-_wwan_pco_type.md">WWAN_PCO_TYPE</a>



<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_pco_status.md">NDIS_WWAN_PCO_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/mb-protocol-configuration-operations--pco-">MB Protocol Configuration Operations (PCO)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_PCO_VALUE structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


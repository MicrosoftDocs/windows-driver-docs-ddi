---
UID: NS:wwan._WWAN_USSD_STRING
title: _WWAN_USSD_STRING (wwan.h)
description: The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.
old-location: netvista\wwan_ussd_string.htm
tech.root: netvista
ms.assetid: 9DE6CE5D-9570-4728-ACED-D6863812A3F4
ms.date: 05/02/2018
ms.keywords: "*PWWAN_USSD_STRING, PWWAN_USSD_STRING, PWWAN_USSD_STRING structure pointer [Network Drivers Starting with Windows Vista], WWAN_USSD_STRING, WWAN_USSD_STRING structure [Network Drivers Starting with Windows Vista], _WWAN_USSD_STRING, netvista.wwan_ussd_string, wwan/PWWAN_USSD_STRING, wwan/WWAN_USSD_STRING"
ms.topic: struct
f1_keywords:
 - "wwan/WWAN_USSD_STRING"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
- wwan.h
api_name:
- WWAN_USSD_STRING
product:
- Windows
targetos: Windows
req.typenames: WWAN_USSD_STRING, *PWWAN_USSD_STRING
---

# _WWAN_USSD_STRING structure


## -description


The WWAN_USSD_STRING structure describes an Unstructured Supplementary Service Data (USSD) string.


## -struct-fields




### -field DataCodingScheme

The data coding scheme that specifies how the <b>String</b> member is encoded, as defined in 3GPP TS 23.038, section 5.


### -field StringLength

The length, in bytes, of USSD string in stored in the <b>String</b> member.


### -field String

 




#### - String[WWAN_USSD_STRING_LEN_MAX]

The USSD string encoded according to the <b>DataCodingScheme</b> member.


## -remarks



<b>StringLength</b> can be from 1 to 160 bytes. Specify 0 bytes to indicate an absent USSD string.

This structure is designed for USSD Stage 2 (3GPP 23.090) and eliminates the need to perform any interpretation of the USSD string in the miniport driver or MB device. If the miniport driver or MB device supports USSD Stage 1 and the network uses USSD Stage 1 then the miniport driver or MB device must transcode between ASCII (IA5) used in USSD Stage 1 and this structure:

For USSD requests, the miniport driver or MB device must decode the USSD string from the GSM-7 bit default alphabet used at requests to ASCII.

For USSD notifications, the miniport driver or MB device must encode the USSD string from ASCII to GSM-7 bit and set the <b>DataCodingScheme</b> member to indicate that the GSM-7 bit default alphabet is used.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_ussd_event">WWAN_USSD_EVENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_ussd_request">WWAN_USSD_REQUEST</a>
 

 


---
UID: NC:bthsdpddi.PRETRIEVEUINT64
title: PRETRIEVEUINT64
author: windows-driver-content
description: The Bluetooth SdpRetrieveUint128 function is used to copy an unaligned 128-bit integer from an SDP stream.
old-location: bltooth\sdpretrieveuint128.htm
old-project: bltooth
ms.assetid: fa187750-1aed-4e74-8e98-a3b8c731f1d1
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpretrieveuint128, SdpRetrieveUint128 callback function [Bluetooth Devices], SdpRetrieveUint128, PRETRIEVEUINT64, PRETRIEVEUINT64, sdplib/SdpRetrieveUint128, bth_funcs_5377ee2b-643e-4486-9eb2-6d37bda46c85.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	sdplib.h
apiname:
-	SdpRetrieveUint128
product: Windows
targetos: Windows
req.typenames: "*PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND"
---

# PRETRIEVEUINT64 callback


## -description


The Bluetooth 
  <b>SdpRetrieveUint128</b> function is used to copy an unaligned 128-bit integer from an SDP stream.


## -prototype


````
PRETRIEVEUINT64 SdpRetrieveUint128;

void SdpRetrieveUint128(
   PUCHAR                 Stream,
   PSDP_ULARGE_INTEGER_16 pUint128
)
{ ... }
````


## -parameters




### -param Stream

A pointer to an unaligned 128-bit integer.


### -param pUint16






#### - pUint128

A pointer to an aligned variable to receive the 128-bit integer.


## -returns


None



## -remarks


The 
    <b>SdpRetrieveUint128</b> function does not search for the unaligned integer to copy. The 
    <i>Stream</i> parameter must specify the exact address of the unsigned integer to be extracted.

Some processor architectures require that values be aligned in memory and will generate an error if an
    attempt is made to access a misaligned value. SDP records are constructed without regard to processor
    alignment rules. When SDP records are stored in memory, they might contain elements that are misaligned
    according to local processor's alignment rules.

The 
    <b>SdpRetrieveUint128</b> function safely copies unaligned integers on computers that have alignment
    requirements and efficiently copies unaligned integers on computers that do not have requirements. In
    addition, this function works on integers that are aligned correctly.

This function has no effect on byte order.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <mshelp:link keywords="bltooth.bthddi_sdp_parse_interface" tabindex="0"><b>
    BTHDDI_SDP_PARSE_INTERFACE</b></mshelp:link> structure.



## -see-also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PRETRIEVEUINT64 callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


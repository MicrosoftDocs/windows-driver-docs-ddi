---
UID: NC:bthsdpddi.PVALIDATESTREAM
title: PVALIDATESTREAM
author: windows-driver-content
description: The Bluetooth SdpValidateStream function is used to parse a raw SDP record and determine if it contains errors.
old-location: bltooth\sdpvalidatestream.htm
old-project: bltooth
ms.assetid: cd119590-b910-487f-b611-5ef59204a798
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpvalidatestream, SdpValidateStream callback function [Bluetooth Devices], SdpValidateStream, PVALIDATESTREAM, PVALIDATESTREAM, bthsdpddi/SdpValidateStream, bth_funcs_1ba1d0ff-b873-4a38-8c5d-71e8afa35861.xml
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
-	BthSdpddi.h
apiname:
-	SdpValidateStream
product: Windows
targetos: Windows
req.typenames: "*PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND"
---

# PVALIDATESTREAM callback


## -description


The Bluetooth 
  <b>SdpValidateStream</b> function is used to parse a raw SDP record and determine if it contains
  errors.


## -prototype


````
NTSTATUS SdpValidateStream(
   PUCHAR     Stream,
   ULONG      Size,
   PULONG_PTR ErrorByte
);
````


## -parameters




#### - Stream

A pointer to the raw SDP stream to be validated.


#### - Size

An unsigned long integer that indicates the size of the SDP stream to be validated.


#### - ErrorByte

A pointer to a variable that receives the address of the first byte in the SDP record that
     contains an error. The address is absolute.


## -returns


Possible return values include:


<dl>
<dt>STATUS_SUCCESS
      </dt>
<dt>STATUS_INVALID_PARAMETER</dt>
</dl>




## -remarks


The 
    <b>SdpValidateStream</b> function does nothing on success. On failure, it pinpoints the location of the
    first error in the specified SDP record.

Bluetooth profile drivers should use this function to validate all SDP streams from external sources.
    Other SDP functions might not perform complete data validation.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <mshelp:link keywords="bltooth.bthddi_sdp_parse_interface" tabindex="0"><b>
    BTHDDI_SDP_PARSE_INTERFACE</b></mshelp:link> structure.



## -see-also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PVALIDATESTREAM callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


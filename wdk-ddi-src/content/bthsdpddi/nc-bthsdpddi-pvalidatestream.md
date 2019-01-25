---
UID: NC:bthsdpddi.PVALIDATESTREAM
title: PVALIDATESTREAM (bthsdpddi.h)
description: The Bluetooth SdpValidateStream function is used to parse a raw SDP record and determine if it contains errors.
old-location: bltooth\sdpvalidatestream.htm
tech.root: bltooth
ms.assetid: cd119590-b910-487f-b611-5ef59204a798
ms.date: 04/27/2018
ms.keywords: PVALIDATESTREAM, PVALIDATESTREAM callback, SdpValidateStream, SdpValidateStream callback function [Bluetooth Devices], bltooth.sdpvalidatestream, bth_funcs_1ba1d0ff-b873-4a38-8c5d-71e8afa35861.xml, bthsdpddi/SdpValidateStream
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	BthSdpddi.h
api_name:
-	SdpValidateStream
product:
- Windows
targetos: Windows
req.typenames: 
---

# PVALIDATESTREAM callback function


## -description


The Bluetooth 
  <b>SdpValidateStream</b> function is used to parse a raw SDP record and determine if it contains
  errors.


## -parameters




### -param Stream

A pointer to the raw SDP stream to be validated.


### -param Size

An unsigned long integer that indicates the size of the SDP stream to be validated.


### -param ErrorByte

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
    <a href="https://msdn.microsoft.com/bb8a1dd5-8207-4034-993e-eed49dc0f9c4">
    BTHDDI_SDP_PARSE_INTERFACE</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536636">BTHDDI_SDP_PARSE_INTERFACE</a>
 

 


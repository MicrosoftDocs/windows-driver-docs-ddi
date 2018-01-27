---
UID: NC:bthsdpddi.PBYTESWAPUINT128
title: PBYTESWAPUINT128
author: windows-driver-content
description: The Bluetooth SdpByteSwapUint128 function is used to reverse the byte order of an unsigned 128-bit integer.
old-location: bltooth\sdpbyteswapuint128.htm
old-project: bltooth
ms.assetid: 04a3400a-e526-47d2-a602-6ecaa7ee7fcf
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: bltooth.sdpbyteswapuint128, SdpByteSwapUint128 callback function [Bluetooth Devices], SdpByteSwapUint128, PBYTESWAPUINT128, PBYTESWAPUINT128, sdplib/SdpByteSwapUint128, bth_funcs_48f64465-c4dd-4cf2-8655-b55d5f0c89ba.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthsdpddi.h
req.include-header: BthSdpddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
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
req.irql: <= PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	sdplib.h
apiname: 
-	SdpByteSwapUint128
product: Windows
targetos: Windows
req.typenames: *PBTH_VENDOR_SPECIFIC_COMMAND, BTH_VENDOR_SPECIFIC_COMMAND
---

# PBYTESWAPUINT128 callback


## -description


The Bluetooth 
  <b>SdpByteSwapUint128</b> function is used to reverse the byte order of an unsigned 128-bit integer.


## -prototype


````
PBYTESWAPUINT128 SdpByteSwapUint128;

void SdpByteSwapUint128(
   PSDP_ULARGE_INTEGER_16 pInUint128,
   PSDP_ULARGE_INTEGER_16 pOutUint128
)
{ ... }
````


## -parameters




### -param pInUint128

A pointer to an unsigned 128-bit integer for which to reverse the byte order.


### -param pOutUint128

A pointer to a variable that receives the converted 128-bit integer.


## -returns


None



## -remarks


The 
    <b>SdpByteSwapUint128</b> function always reverses the byte order of the value passed in the 
    <i>pInUint128</i> parameter. Writers of Bluetooth device drivers can use this function to convert unsigned
    128-bit integer values from the byte order on the local computer to the byte order of the network that
    the computer is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>.



## -see-also

<a href="..\bthsdpddi\ns-bthsdpddi-_bthddi_sdp_parse_interface.md">BTHDDI_SDP_PARSE_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20PBYTESWAPUINT128 callback function%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


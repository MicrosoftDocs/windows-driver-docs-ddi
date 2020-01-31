---
UID: NC:bthsdpddi.PBYTESWAPUINT128
title: PBYTESWAPUINT128 (bthsdpddi.h)
description: The Bluetooth SdpByteSwapUint128 function is used to reverse the byte order of an unsigned 128-bit integer.
old-location: bltooth\sdpbyteswapuint128.htm
tech.root: bltooth
ms.assetid: 04a3400a-e526-47d2-a602-6ecaa7ee7fcf
ms.date: 04/27/2018
ms.keywords: PBYTESWAPUINT128, PBYTESWAPUINT128 callback, SdpByteSwapUint128, SdpByteSwapUint128 callback function [Bluetooth Devices], bltooth.sdpbyteswapuint128, bth_funcs_48f64465-c4dd-4cf2-8655-b55d5f0c89ba.xml, sdplib/SdpByteSwapUint128
f1_keywords:
 - "bthsdpddi/SdpByteSwapUint128"
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
req.irql: <= PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- sdplib.h
api_name:
- SdpByteSwapUint128
product:
- Windows
targetos: Windows
req.typenames: 
---

# PBYTESWAPUINT128 callback function


## -description


The Bluetooth 
  <b>SdpByteSwapUint128</b> function is used to reverse the byte order of an unsigned 128-bit integer.


## -parameters




### -param pInUint128

A pointer to an unsigned 128-bit integer for which to reverse the byte order.


### -param pOutUint128

A pointer to a variable that receives the converted 128-bit integer.


## -remarks



The 
    <b>SdpByteSwapUint128</b> function always reverses the byte order of the value passed in the 
    <i>pInUint128</i> parameter. Writers of Bluetooth device drivers can use this function to convert unsigned
    128-bit integer values from the byte order on the local computer to the byte order of the network that
    the computer is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
 

 


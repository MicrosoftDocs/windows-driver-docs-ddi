---
UID: NC:bthsdpddi.PBYTESWAPUINT64
title: PBYTESWAPUINT64 (bthsdpddi.h)
description: The Bluetooth SdpByteSwapUint64 function is used to reverse the byte order of an unsigned 64-bit integer.
old-location: bltooth\sdpbyteswapuint64.htm
tech.root: bltooth
ms.assetid: aa3c83fb-72fb-4709-8c5d-982814ddbcd0
ms.date: 04/27/2018
keywords: ["PBYTESWAPUINT64 callback function"]
ms.keywords: PBYTESWAPUINT64, PBYTESWAPUINT64 callback, SdpByteSwapUint64, SdpByteSwapUint64 callback function [Bluetooth Devices], bltooth.sdpbyteswapuint64, bth_funcs_b5fdae49-077b-43f8-a4c2-cd380422d560.xml, sdplib/SdpByteSwapUint64
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PBYTESWAPUINT64
 - bthsdpddi/PBYTESWAPUINT64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - sdplib.h
api_name:
 - SdpByteSwapUint64
---

# PBYTESWAPUINT64 callback function


## -description

The Bluetooth 
  <b>SdpByteSwapUint64</b> function is used to reverse the byte order of an unsigned 64-bit integer.

## -parameters

### -param uint64

The unsigned 64-bit integer for which to reverse the byte order.

## -returns

<b>SdpByteSwapUint64</b> returns a converted unsigned 64-bit integer.

## -remarks

The 
    <b>SdpByteSwapUint64</b> function always reverses the byte order of the value passed in the 
    <i>uint64</i> parameter. Writers of Bluetooth device drivers can use this function to convert unsigned
    64-bit integer values from the byte order on the local computer to the byte order of the network that the
    computer is connected to.

Bluetooth profile drivers can obtain a pointer to this function through the 
    <a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthsdpddi/ns-bthsdpddi-_bthddi_sdp_parse_interface">BTHDDI_SDP_PARSE_INTERFACE</a>
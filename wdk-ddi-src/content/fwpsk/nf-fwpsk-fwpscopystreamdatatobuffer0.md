---
UID: NF:fwpsk.FwpsCopyStreamDataToBuffer0
title: FwpsCopyStreamDataToBuffer0 function
author: windows-driver-content
description: The FwpsCopyStreamDataToBuffer0 function copies stream data to a buffer.Note  FwpsCopyStreamDataToBuffer0 is a specific version of FwpsCopyStreamDataToBuffer.
old-location: netvista\fwpscopystreamdatatobuffer0.htm
old-project: netvista
ms.assetid: 758733a4-9657-48a4-bbcc-f266c72c1d6a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FwpsCopyStreamDataToBuffer0, FwpsCopyStreamDataToBuffer0 function [Network Drivers Starting with Windows Vista], fwpsk/FwpsCopyStreamDataToBuffer0, netvista.fwpscopystreamdatatobuffer0, wfp_ref_2_funct_3_fwps_C_dc46f99c-31e7-4e45-8f0b-fc3d0a96989e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: Fwpkclnt.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	fwpkclnt.lib
-	fwpkclnt.dll
api_name:
-	FwpsCopyStreamDataToBuffer0
product:
- Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCopyStreamDataToBuffer0 function


## -description


The 
  <b>FwpsCopyStreamDataToBuffer0</b> function copies stream data to a buffer.
<div class="alert"><b>Note</b>  <b>FwpsCopyStreamDataToBuffer0</b> is a specific version of <b>FwpsCopyStreamDataToBuffer</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -parameters




### -param calloutStreamData [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a> structure that contains
     the stream data to be copied.


### -param buffer [in, out]

A pointer to a location in memory that will store the copy of the stream data pointed to by the 
     <i>calloutStreamData</i> parameter. The size of the buffer must be greater than or equal to 
     <i>bytesToCopy</i>.


### -param bytesToCopy [in]

The amount of data, in bytes, to be copied into the receiving buffer.


### -param bytesCopied [out]

A pointer to a variable that receives the size, in bytes, of the stream data copied to the memory
     location pointed to by the 
     <i>buffer</i> parameter.


## -returns



None.




## -remarks



To copy all indicated data to the receiving buffer, ensure that the buffer is at least 
    <i>calloutStreamData</i> -&gt;
    <b>DataLength</b> in size.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552419">FWPS_STREAM_DATA0</a>
 

 


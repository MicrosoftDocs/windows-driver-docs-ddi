---
UID: NF:fwpsk.FwpsCopyStreamDataToBuffer0
title: FwpsCopyStreamDataToBuffer0 function
author: windows-driver-content
description: The FwpsCopyStreamDataToBuffer0 function copies stream data to a buffer.Note  FwpsCopyStreamDataToBuffer0 is a specific version of FwpsCopyStreamDataToBuffer.
old-location: netvista\fwpscopystreamdatatobuffer0.htm
old-project: netvista
ms.assetid: 758733a4-9657-48a4-bbcc-f266c72c1d6a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , 0, B, C, D, F, FwpsCopyStreamDataToBuffer0, FwpsCopyStreamDataToBuffer0 function [Network Drivers Starting with Windows Vista], S, T, a, e, f, fwpsk/FwpsCopyStreamDataToBuffer0, m, netvista.fwpscopystreamdatatobuffer0, o, p, r, s, t, u, w, wfp_ref_2_funct_3_fwps_C_dc46f99c-31e7-4e45-8f0b-fc3d0a96989e.xml, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	fwpkclnt.lib
-	fwpkclnt.dll
apiname:
-	FwpsCopyStreamDataToBuffer0
product: Windows
targetos: Windows
req.typenames: FWPS_VSWITCH_EVENT_TYPE
---

# FwpsCopyStreamDataToBuffer0 function


## -description


The 
  <b>FwpsCopyStreamDataToBuffer0</b> function copies stream data to a buffer.
<div class="alert"><b>Note</b>  <b>FwpsCopyStreamDataToBuffer0</b> is a specific version of <b>FwpsCopyStreamDataToBuffer</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -syntax


````
void NTAPI FwpsCopyStreamDataToBuffer0(
  _In_    const FWPS_STREAM_DATA0 *calloutStreamData,
  _Inout_       PVOID             buffer,
  _In_          SIZE_T            bytesToCopy,
  _Out_         SIZE_T            *bytesCopied
);
````


## -parameters




### -param calloutStreamData [in]

A pointer to a 
     <a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a> structure that contains
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

<a href="..\fwpsk\ns-fwpsk-fwps_stream_data0_.md">FWPS_STREAM_DATA0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FwpsCopyStreamDataToBuffer0 function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


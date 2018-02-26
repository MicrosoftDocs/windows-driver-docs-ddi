---
UID: NS:ks.KSRATE
title: KSRATE
author: windows-driver-content
description: The query is passed a KSRATE structure appended to the property containing the rate request (known as a KSRATE_CAPABILITY structure), and is returned a KSRATE structure filled in with the capability given the rate request.
old-location: stream\ksrate.htm
old-project: stream
ms.assetid: dc8f23d5-14bb-43be-807a-041ca9c30a76
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSRATE, ,, A, E, K, KSRATE, KSRATE structure [Streaming Media Devices], P, PKSRATE, PKSRATE structure pointer [Streaming Media Devices], R, S, T, ks-struct_a47aa4cc-ff36-4a02-bd68-63c7ed450279.xml, ks/KSRATE, ks/PKSRATE, stream.ksrate"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSRATE
product: Windows
targetos: Windows
req.typenames: KSRATE, *PKSRATE
---

# KSRATE structure


## -description


The query is passed a KSRATE structure appended to the property containing the rate request (known as a <a href="..\ks\ns-ks-ksrate_capability.md">KSRATE_CAPABILITY</a> structure), and is returned a KSRATE structure filled in with the capability given the rate request.


## -syntax


````
typedef struct {
  LONGLONG        PresentationStart;
  LONGLONG        Duration;
  KSPIN_INTERFACE Interface;
  LONG            Rate;
  ULONG           Flags;
} KSRATE, *PKSRATE;
````


## -struct-fields




### -field PresentationStart

Specifies the start point for the rate in presentation time units.


### -field Duration

Specifies the duration of the rate in presentation time units.


### -field Interface

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff563537">KSPIN_INTERFACE</a> that specifies either the interface used in the connection this rate request is being sent to, or the interface of a related connection. This allows the time units to be interpreted by the pin.


### -field Rate

Specifies the rate in terms of 1/10th percentage points, where 1000 is the nominal 1.0 rate, 500 is 0.5 rate, and so on. Negative numbers indicate reverse rates.


### -field Flags

Possible flag values are listed in the following table.

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
KSRATE_NOPRESENTATIONSTART

</td>
<td>
Specifies that there is no valid start time in this rate change request or query.

</td>
</tr>
<tr>
<td>
KSRATE_NOPRESENTATIONDURATION

</td>
<td>
Specifies that there is no valid duration in this rate change request or query.

</td>
</tr>
</table>
 


## -see-also

<a href="..\ks\ns-ks-ksrate_capability.md">KSRATE_CAPABILITY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSRATE structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


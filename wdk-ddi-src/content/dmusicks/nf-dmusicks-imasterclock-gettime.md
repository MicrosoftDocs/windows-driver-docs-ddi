---
UID: NF:dmusicks.IMasterClock.GetTime
title: IMasterClock::GetTime method
author: windows-driver-content
description: The GetTime method retrieves the current reference time read from the master clock.
old-location: audio\imasterclock_gettime.htm
old-project: audio
ms.assetid: 9e88a94d-ce25-43ee-8187-30b406e8d9e4
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IMasterClock, IMasterClock::GetTime, GetTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
req.include-header: Dmusicks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMasterClock.GetTime
req.alt-loc: dmusicks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.typenames: DMUS_STREAM_TYPE
---

# IMasterClock::GetTime method



## -description
The <code>GetTime</code> method retrieves the current reference time read from the master clock.



## -syntax

````
NTSTATUS GetTime(
  [out] REFERENCE_TIME *prtTime
);
````


## -parameters

### -param prtTime [out]

Output pointer for the reference time. This parameter points to a caller-allocated variable into which the method writes the reference time. Reference time is measured in 100-nanosecond units.


## -returns
<code>GetTime</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dmusicks\nn-dmusicks-imasterclock.md">IMasterClock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMasterClock::GetTime method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


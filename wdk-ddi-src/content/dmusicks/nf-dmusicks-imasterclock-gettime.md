---
UID: NF:dmusicks.IMasterClock.GetTime
title: IMasterClock::GetTime method
author: windows-driver-content
description: The GetTime method retrieves the current reference time read from the master clock.
old-location: audio\imasterclock_gettime.htm
old-project: audio
ms.assetid: 9e88a94d-ce25-43ee-8187-30b406e8d9e4
ms.author: windowsdriverdev
ms.date: 3/19/2018
ms.keywords: GetTime method [Audio Devices], GetTime method [Audio Devices], IMasterClock interface, GetTime,IMasterClock.GetTime, IMasterClock, IMasterClock interface [Audio Devices], GetTime method, IMasterClock::GetTime, audio.imasterclock_gettime, audmp-routines_08af6e05-c432-4560-91fb-f17687291fc0.xml, dmusicks/IMasterClock::GetTime
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dmusicks.h
api_name:
-	IMasterClock.GetTime
product:
- Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IMasterClock::GetTime method


## -description


The <code>GetTime</code> method retrieves the current reference time read from the master clock.


## -parameters




### -param pTime [out]

Output pointer for the reference time. This parameter points to a caller-allocated variable into which the method writes the reference time. Reference time is measured in 100-nanosecond units.


## -returns



<code>GetTime</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536696">IMasterClock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536701">IMiniportDMus::NewStream</a>
 

 


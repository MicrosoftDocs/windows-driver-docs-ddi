---
UID: NF:dmusicks.IMasterClock.GetTime
title: IMasterClock::GetTime (dmusicks.h)
description: The GetTime method retrieves the current reference time read from the master clock.
old-location: audio\imasterclock_gettime.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IMasterClock::GetTime"]
ms.keywords: GetTime, GetTime method [Audio Devices], GetTime method [Audio Devices],IMasterClock interface, IMasterClock interface [Audio Devices],GetTime method, IMasterClock.GetTime, IMasterClock::GetTime, audio.imasterclock_gettime, audmp-routines_08af6e05-c432-4560-91fb-f17687291fc0.xml, dmusicks/IMasterClock::GetTime
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IMasterClock::GetTime
 - dmusicks/IMasterClock::GetTime
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dmusicks.h
api_name:
 - IMasterClock::GetTime
---

# IMasterClock::GetTime


## -description

The <code>GetTime</code> method retrieves the current reference time read from the master clock.

## -parameters

### -param pTime 

[out]
Output pointer for the reference time. This parameter points to a caller-allocated variable into which the method writes the reference time. Reference time is measured in 100-nanosecond units.

## -returns

<code>GetTime</code> returns S_OK if the call was successful. Otherwise, the method returns an appropriate error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-imasterclock">IMasterClock</a>



<a href="/windows-hardware/drivers/ddi/dmusicks/nf-dmusicks-iminiportdmus-newstream">IMiniportDMus::NewStream</a>


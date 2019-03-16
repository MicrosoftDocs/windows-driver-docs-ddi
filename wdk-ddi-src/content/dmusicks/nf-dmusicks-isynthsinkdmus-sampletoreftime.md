---
UID: NF:dmusicks.ISynthSinkDMus.SampleToRefTime
title: ISynthSinkDMus::SampleToRefTime (dmusicks.h)
description: The SampleToRefTime method converts a sample time to a reference time.
old-location: audio\isynthsinkdmus_sampletoreftime.htm
tech.root: audio
ms.assetid: b2d54ee9-78aa-4799-a06d-6c79000d3e32
ms.date: 05/08/2018
ms.keywords: ISynthSinkDMus interface [Audio Devices],SampleToRefTime method, ISynthSinkDMus.SampleToRefTime, ISynthSinkDMus::SampleToRefTime, SampleToRefTime, SampleToRefTime method [Audio Devices], SampleToRefTime method [Audio Devices],ISynthSinkDMus interface, audio.isynthsinkdmus_sampletoreftime, audmp-routines_acfbec43-3c33-4d78-9d25-57e44afe0033.xml, dmusicks/ISynthSinkDMus::SampleToRefTime
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dmusicks.h
api_name:
- ISynthSinkDMus.SampleToRefTime
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISynthSinkDMus::SampleToRefTime


## -description


The <code>SampleToRefTime</code> method converts a sample time to a reference time.


## -parameters




### -param llSampleTime [in]

Specifies the sample time being passed in.


### -param prfTime [out]

Output pointer for the reference time. This parameter is a pointer to a caller-allocated variable into which the method writes the calculated reference time. Reference time is measured in 100-nanosecond units.


## -returns



<code>SampleToRefTime</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>SampleToRefTime</code> method accepts a sample time as an input parameter, converts the sample time to a reference time, and outputs the reference time to a location specified by the caller.

The calculation of reference time from sample time to reference time depends on the sampling frequency. For example, if the output buffer is in a 44.2 kHz format, a sample time of 44,200 is equivalent to a reference time of one second.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536526">IDirectMusicSynthSink::SampleToRefTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537011">ISynthSinkDMus</a>
 

 


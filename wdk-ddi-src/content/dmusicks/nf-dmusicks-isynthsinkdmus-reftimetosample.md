---
UID: NF:dmusicks.ISynthSinkDMus.RefTimeToSample
title: ISynthSinkDMus::RefTimeToSample (dmusicks.h)
description: The RefTimeToSample method converts a reference time into a sample time.
old-location: audio\isynthsinkdmus_reftimetosample.htm
tech.root: audio
ms.assetid: 20906bcd-3059-4d10-92cb-8efdef929ccd
ms.date: 05/08/2018
ms.keywords: ISynthSinkDMus interface [Audio Devices],RefTimeToSample method, ISynthSinkDMus.RefTimeToSample, ISynthSinkDMus::RefTimeToSample, RefTimeToSample, RefTimeToSample method [Audio Devices], RefTimeToSample method [Audio Devices],ISynthSinkDMus interface, audio.isynthsinkdmus_reftimetosample, audmp-routines_8c8379c0-db14-4275-adfc-2dd595879feb.xml, dmusicks/ISynthSinkDMus::RefTimeToSample
f1_keywords:
 - "dmusicks/ISynthSinkDMus.RefTimeToSample"
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
- ISynthSinkDMus.RefTimeToSample
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISynthSinkDMus::RefTimeToSample


## -description


The <code>RefTimeToSample</code> method converts a reference time into a sample time.


## -parameters




### -param rfTime [in]

Pointer to the reference time being passed in. The reference time is measured in 100-nanosecond units.


### -param pllSampleTime [out]

Output pointer for the sample time. This parameter points to a caller-allocated variable into which the method writes the calculated sample time.


## -returns



<code>RefTimeToSample</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>RefTimeToSample</code> method converts reference time to sample time. The method takes a reference time as an input parameter, and it outputs the corresponding sample time.

The calculation of the reference time from the sample time depends on the sampling frequency. For example, if the output buffer is in a 44.1 kHz format, a sample time of 44,100 is equivalent to a reference time of one second.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/dmusics/nf-dmusics-idirectmusicsynthsink-reftimetosample">IDirectMusicSynthSink::RefTimeToSample</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dmusicks/nn-dmusicks-isynthsinkdmus">ISynthSinkDMus</a>
 

 


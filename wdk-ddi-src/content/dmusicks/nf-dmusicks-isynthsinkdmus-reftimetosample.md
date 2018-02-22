---
UID: NF:dmusicks.ISynthSinkDMus.RefTimeToSample
title: ISynthSinkDMus::RefTimeToSample method
author: windows-driver-content
description: The RefTimeToSample method converts a reference time into a sample time.
old-location: audio\isynthsinkdmus_reftimetosample.htm
old-project: audio
ms.assetid: 20906bcd-3059-4d10-92cb-8efdef929ccd
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: RefTimeToSample method [Audio Devices], ISynthSinkDMus interface, ISynthSinkDMus, ISynthSinkDMus interface [Audio Devices], RefTimeToSample method, RefTimeToSample, audmp-routines_8c8379c0-db14-4275-adfc-2dd595879feb.xml, dmusicks/ISynthSinkDMus::RefTimeToSample, audio.isynthsinkdmus_reftimetosample, ISynthSinkDMus::RefTimeToSample, RefTimeToSample method [Audio Devices]
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
req.lib: dmusicks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dmusicks.h
apiname:
-	ISynthSinkDMus.RefTimeToSample
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# ISynthSinkDMus::RefTimeToSample method


## -description


The <code>RefTimeToSample</code> method converts a reference time into a sample time.


## -syntax


````
NTSTATUS RefTimeToSample(
  [in]  REFERENCE_TIME rtTime,
  [out] LONGLONG       *pllSampleTime
);
````


## -parameters




### -param rfTime




### -param pllSampleTime [out]

Output pointer for the sample time. This parameter points to a caller-allocated variable into which the method writes the calculated sample time.


#### - rtTime [in]

Pointer to the reference time being passed in. The reference time is measured in 100-nanosecond units.


## -returns



<code>RefTimeToSample</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The <code>RefTimeToSample</code> method converts reference time to sample time. The method takes a reference time as an input parameter, and it outputs the corresponding sample time.

The calculation of the reference time from the sample time depends on the sampling frequency. For example, if the output buffer is in a 44.1 kHz format, a sample time of 44,100 is equivalent to a reference time of one second.




## -see-also

<a href="..\dmusicks\nn-dmusicks-isynthsinkdmus.md">ISynthSinkDMus</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536525">IDirectMusicSynthSink::RefTimeToSample</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20ISynthSinkDMus::RefTimeToSample method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


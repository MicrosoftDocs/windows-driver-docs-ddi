---
UID: NF:wdm.RtlTimeFieldsToTime
title: RtlTimeFieldsToTime function
author: windows-driver-content
description: The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value.
old-location: kernel\rtltimefieldstotime.htm
old-project: kernel
ms.assetid: 5873b627-6ef4-4e2c-8a53-921f37b729bc
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlTimeFieldsToTime, RtlTimeFieldsToTime routine [Kernel-Mode Driver Architecture], k109_9b5d67de-92c3-4fb7-bcd7-4e045ae9ada4.xml, kernel.rtltimefieldstotime, wdm/RtlTimeFieldsToTime
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlTimeFieldsToTime
product: Windows
targetos: Windows
req.typenames: 
---

# RtlTimeFieldsToTime function


## -description


The <b>RtlTimeFieldsToTime</b> routine converts <b>TIME_FIELDS</b> information to a system time value.


## -parameters




### -param TimeFields [in]

Pointer to the following structure, containing the time information to be converted:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct TIME_FIELDS {
    CSHORT Year;
    CSHORT Month;
    CSHORT Day;
    CSHORT Hour;
    CSHORT Minute;
    CSHORT Second;
    CSHORT Milliseconds;
    CSHORT Weekday;
} TIME_FIELDS;</pre>
</td>
</tr>
</table></span></div>




#### Year

Specifies a value from 1601 on.



#### Month

Specifies a value from 1 to 12.



#### Day

Specifies a value from 1 to 31.



#### Hour

Specifies a value from 0 to 23.



#### Minute

Specifies a value from 0 to 59.



#### Second

Specifies a value from 0 to 59.



#### Milliseconds

Specifies a value from 0 to 999.



#### Weekday

Specifies a value from 0 to 6 (Sunday to Saturday). 


### -param Time [out]

Pointer to a buffer, which is to contain the converted system time value as a large integer. 


## -returns



<b>RtlTimeFieldsToTime</b> returns <b>TRUE</b> if the input <i>TimeFields</i> data was successfully converted.




## -remarks



<b>RtlTimeFieldsToTime</b> ignores the <b>Weekday</b> value in <i>TimeFields</i>.

Callers of <b>RtlTimeFieldsToTime</b> can be running at any IRQL if both input buffers are resident.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545483">ExLocalTimeToSystemTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545622">ExSystemTimeToLocalTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553068">KeQuerySystemTime</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562884">RtlTimeToTimeFields</a>
 

 


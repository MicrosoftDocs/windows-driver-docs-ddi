---
UID: NF:wdm.RtlTimeFieldsToTime
title: RtlTimeFieldsToTime function
author: windows-driver-content
description: The RtlTimeFieldsToTime routine converts TIME_FIELDS information to a system time value.
old-location: kernel\rtltimefieldstotime.htm
old-project: kernel
ms.assetid: 5873b627-6ef4-4e2c-8a53-921f37b729bc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlTimeFieldsToTime routine [Kernel-Mode Driver Architecture], k109_9b5d67de-92c3-4fb7-bcd7-4e045ae9ada4.xml, kernel.rtltimefieldstotime, wdm/RtlTimeFieldsToTime, RtlTimeFieldsToTime
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlTimeFieldsToTime
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlTimeFieldsToTime function


## -description


The <b>RtlTimeFieldsToTime</b> routine converts <b>TIME_FIELDS</b> information to a system time value.


## -syntax


````
BOOLEAN RtlTimeFieldsToTime(
  _In_  PTIME_FIELDS   TimeFields,
  _Out_ PLARGE_INTEGER Time
);
````


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

<a href="..\wdm\nf-wdm-exlocaltimetosystemtime.md">ExLocalTimeToSystemTime</a>

<a href="..\wdm\nf-wdm-kequerysystemtime.md">KeQuerySystemTime</a>

<a href="..\wdm\nf-wdm-exsystemtimetolocaltime.md">ExSystemTimeToLocalTime</a>

<a href="..\wdm\nf-wdm-rtltimetotimefields.md">RtlTimeToTimeFields</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlTimeFieldsToTime routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


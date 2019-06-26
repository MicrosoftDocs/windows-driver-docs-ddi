---
UID: NF:storport.StorPortQueryPerformanceCounter
title: StorPortQueryPerformanceCounter function (storport.h)
description: The current system performance counter value is queried is returned by the StorPortQueryPerformanceCounter routine.
old-location: storage\storportqueryperformancecounter.htm
tech.root: storage
ms.assetid: 6502E3AE-5841-41C9-BEB7-B00620DBF02D
ms.date: 03/29/2018
ms.keywords: StorPortQueryPerformanceCounter, StorPortQueryPerformanceCounter routine [Storage Devices], storage.storportqueryperformancecounter, storport/StorPortQueryPerformanceCounter
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Storport.h
api_name:
- StorPortQueryPerformanceCounter
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortQueryPerformanceCounter function


## -description


The current system performance counter value is queried is returned by the <b>StorPortQueryPerformanceCounter</b> routine.. The performance frequency is also returned as an optional parameter.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension for the host bus adapter (HBA).


### -param PerformanceFrequency [out, optional]

 A pointer to a large integer to receive the current system performance frequency value. This parameter is optional and can be NULL.


### -param PerformanceCounter [out]

A pointer to a large integer to receive the current system performance counter value.


## -returns



<b>StorPortQueryPerformanceCounter</b> returns one of the following status codes:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The performance counter value is returned in the large integer pointed to by <i>PerformanceCounter</i>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>PerformanceCounter</i> parameter is <b>NULL</b>.

</td>
</tr>
</table>
 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/storport/nf-storport-storportquerysystemtime">StorPortQuerySystemTime</a>
 

 


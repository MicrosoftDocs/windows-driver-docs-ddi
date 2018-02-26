---
UID: NS:ksmedia.KSPROPERTY_TUNER_SCAN_STATUS_S
title: KSPROPERTY_TUNER_SCAN_STATUS_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation.
old-location: stream\ksproperty_tuner_scan_status_s.htm
old-project: stream
ms.assetid: b09373ef-7b65-46f7-b5b7-a6dcecf0166c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_TUNER_SCAN_STATUS_S, ,, A, C, E, K, KSPROPERTY_TUNER_SCAN_STATUS_S, KSPROPERTY_TUNER_SCAN_STATUS_S structure [Streaming Media Devices], N, O, P, PKSPROPERTY_TUNER_SCAN_STATUS_S, PKSPROPERTY_TUNER_SCAN_STATUS_S structure pointer [Streaming Media Devices], R, S, T, U, Y, _, ksmedia/KSPROPERTY_TUNER_SCAN_STATUS_S, ksmedia/PKSPROPERTY_TUNER_SCAN_STATUS_S, stream.ksproperty_tuner_scan_status_s, vidcapstruct_70c7d301-6c91-4955-bcaa-67cad29cb15a.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the operating system.
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
-	ksmedia.h
apiname:
-	KSPROPERTY_TUNER_SCAN_STATUS_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_TUNER_SCAN_STATUS_S, *PKSPROPERTY_TUNER_SCAN_STATUS_S
---

# KSPROPERTY_TUNER_SCAN_STATUS_S structure


## -description


The KSPROPERTY_TUNER_SCAN_STATUS_S structure describes status for a scanning operation.


## -syntax


````
typedef struct {
  KSPROPERTY    Property;
  TunerLockType LockStatus;
  ULONG         CurrentFrequency;
} KSPROPERTY_TUNER_SCAN_STATUS_S, *PKSPROPERTY_TUNER_SCAN_STATUS_S;
````


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field LockStatus

One of the following values from the <b>TunerLockType</b> enumeration that indicates the lock status of the scanning operation.

<table>
<tr>
<th>Status</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>Tuner_LockType_None</b> (0x00)

</td>
<td>
The tuner is not locked on a signal. The driver can return this value at the end of a scan.

</td>
</tr>
<tr>
<td>
<b>Tuner_LockType_Within_Scan_Sensing_Range</b> (0x01)

</td>
<td>
The signal is nearby; however, the driver cannot report the exact frequency.

</td>
</tr>
<tr>
<td>
<b>Tuner_LockType_Locked</b> (0x02)

</td>
<td>
A fine-tune signal lock was established. The driver can return this value at the end of a scan.

</td>
</tr>
</table>
 


### -field CurrentFrequency

The current locked-in frequency, in Hz, on the tuning device. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565893">KSPROPERTY_TUNER_SCAN_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561898">KSEVENT_TUNER_INITIATE_SCAN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_SCAN_STATUS_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


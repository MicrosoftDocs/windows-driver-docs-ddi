---
UID: NS:ksmedia._KSDEVICE_PROFILE_INFO
title: _KSDEVICE_PROFILE_INFO (ksmedia.h)
description: The KSDEVICE_PROFILE_INFO is a generic structure designed to handle profile information for various device types.
old-location: stream\ksdevice_profile_info.htm
tech.root: stream
ms.assetid: 32C894CA-B644-4221-97B6-A21F2A459DE6
ms.date: 04/23/2018
ms.keywords: "*PKSDEVICE_PROFILE_INFO, KSDEVICE_PROFILE_INFO, KSDEVICE_PROFILE_INFO structure [Streaming Media Devices], PKSDEVICE_PROFILE_INFO, PKSDEVICE_PROFILE_INFO structure pointer [Streaming Media Devices], _KSDEVICE_PROFILE_INFO, ksmedia/KSDEVICE_PROFILE_INFO, ksmedia/PKSDEVICE_PROFILE_INFO, stream.ksdevice_profile_info"
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSDEVICE_PROFILE_INFO
product:
- Windows
targetos: Windows
req.typenames: KSDEVICE_PROFILE_INFO, *PKSDEVICE_PROFILE_INFO
---

# _KSDEVICE_PROFILE_INFO structure


## -description


The <b>KSDEVICE_PROFILE_INFO</b> is a generic structure designed to handle profile information for various device types.


## -struct-fields




### -field Type

Defines the type of profile. Currently, the only defined type is <b>KSDEVICE_PROFILE_TYPE_CAMERA</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define KSDEVICE_PROFILE_TYPE_CAMERA    0x00000001</pre>
</td>
</tr>
</table></span></div>

### -field Size

This must be set to sizeof(KSDEVICE_PROFILE_INFO) structure.


### -field Camera

<b>Info</b>

Structure of <a href="https://msdn.microsoft.com/library/windows/hardware/dn925214">KSCAMERA_PROFILE_INFO</a> defining the profile information of a camera.

<b>Reserved</b>

Unused.  Must be set to 0.

<b>ConcurrencyCount</b>

Number of <a href="https://msdn.microsoft.com/library/windows/hardware/dn925213">KSCAMERA_PROFILE_CONCURRENCYINFO</a> structures in the <b>Concurrency</b> array.

For Windows 10 this must be less than or equal 1.

A value of 0 with <b>Concurrency</b> set to <b>NULL</b>, indicates this profile is non-concurrent.

<b>Concurrency</b>

An array of <b>KSCAMERA_PROFILE_CONCURRENCYINFO</b> structures describing the concurrency support for this profile.

If <b>CountOfConcurrency</b> is 0, this parameter must be <b>NULL</b>.

If <b>CountOfConcurrency</b> is greater than 0, this parameter must not be <b>NULL</b>.


### -field Camera.Info

 


### -field Camera.Reserved

 


### -field Camera.ConcurrencyCount

 


### -field Camera.Concurrency

 




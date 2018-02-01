---
UID: NS:ksmedia._KSDEVICE_PROFILE_INFO
title: "_KSDEVICE_PROFILE_INFO"
author: windows-driver-content
description: The KSDEVICE_PROFILE_INFO is a generic structure designed to handle profile information for various device types.
old-location: stream\ksdevice_profile_info.htm
old-project: stream
ms.assetid: 32C894CA-B644-4221-97B6-A21F2A459DE6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSDEVICE_PROFILE_INFO, KSDEVICE_PROFILE_INFO, ksmedia/PKSDEVICE_PROFILE_INFO, PKSDEVICE_PROFILE_INFO, _KSDEVICE_PROFILE_INFO, PKSDEVICE_PROFILE_INFO structure pointer [Streaming Media Devices], ksmedia/KSDEVICE_PROFILE_INFO, stream.ksdevice_profile_info, KSDEVICE_PROFILE_INFO structure [Streaming Media Devices]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSDEVICE_PROFILE_INFO
product: Windows
targetos: Windows
req.typenames: KSDEVICE_PROFILE_INFO, *PKSDEVICE_PROFILE_INFO
---

# _KSDEVICE_PROFILE_INFO structure


## -description


The <b>KSDEVICE_PROFILE_INFO</b> is a generic structure designed to handle profile information for various device types.


## -syntax


````
typedef struct _KSDEVICE_PROFILE_INFO {
  UINT32 Type;
  UINT32 Size;
  union {
    struct {
      KSCAMERA_PROFILE_INFO             Info;
      UINT32                            Reserved;
      UINT32                            ConcurrencyCount;
      PKSCAMERA_PROFILE_CONCURRENCYINFO Concurrency;
    } Camera;
  };
} KSDEVICE_PROFILE_INFO, *PKSDEVICE_PROFILE_INFO;
````


## -struct-fields




### -field Camera

<b>Info</b>

Structure of <a href="..\ksmedia\ns-ksmedia-_kscamera_profile_info.md">KSCAMERA_PROFILE_INFO</a> defining the profile information of a camera.

<b>Reserved</b>

Unused.  Must be set to 0.

<b>ConcurrencyCount</b>

Number of <a href="..\ksmedia\ns-ksmedia-_kscamera_profile_concurrencyinfo.md">KSCAMERA_PROFILE_CONCURRENCYINFO</a> structures in the <b>Concurrency</b> array.

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


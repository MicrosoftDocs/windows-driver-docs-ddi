---
UID: NS:ksmedia._KSDEVICE_PROFILE_INFO
title: _KSDEVICE_PROFILE_INFO (ksmedia.h)
description: The KSDEVICE_PROFILE_INFO is a generic structure designed to handle profile information for various device types.
old-location: stream\ksdevice_profile_info.htm
tech.root: stream
ms.assetid: 32C894CA-B644-4221-97B6-A21F2A459DE6
ms.date: 04/23/2018
keywords: ["KSDEVICE_PROFILE_INFO structure"]
ms.keywords: "*PKSDEVICE_PROFILE_INFO, KSDEVICE_PROFILE_INFO, KSDEVICE_PROFILE_INFO structure [Streaming Media Devices], PKSDEVICE_PROFILE_INFO, PKSDEVICE_PROFILE_INFO structure pointer [Streaming Media Devices], _KSDEVICE_PROFILE_INFO, ksmedia/KSDEVICE_PROFILE_INFO, ksmedia/PKSDEVICE_PROFILE_INFO, stream.ksdevice_profile_info"
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
targetos: Windows
req.typenames: KSDEVICE_PROFILE_INFO, *PKSDEVICE_PROFILE_INFO
f1_keywords:
 - _KSDEVICE_PROFILE_INFO
 - ksmedia/_KSDEVICE_PROFILE_INFO
 - PKSDEVICE_PROFILE_INFO
 - ksmedia/PKSDEVICE_PROFILE_INFO
 - KSDEVICE_PROFILE_INFO
 - ksmedia/KSDEVICE_PROFILE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KSDEVICE_PROFILE_INFO
---

# _KSDEVICE_PROFILE_INFO structure


## -description

The **KSDEVICE_PROFILE_INFO** is a generic structure designed to handle profile information for various device types.

## -struct-fields

### -field Type

Defines the type of profile. Currently, the only defined type is **KSDEVICE_PROFILE_TYPE_CAMERA**.

```cpp
#define KSDEVICE_PROFILE_TYPE_CAMERA    0x00000001
```

### -field Size

This must be set to sizeof(KSDEVICE_PROFILE_INFO) structure.

### -field Camera

### -field Camera.Info

Structure of [KSCAMERA_PROFILE_INFO](./ns-ksmedia-_kscamera_profile_info.md) defining the profile information of a camera.

### -field Camera.Reserved

Unused.  Must be set to 0.

### -field Camera.ConcurrencyCount

Number of [KSCAMERA_PROFILE_CONCURRENCYINFO](./ns-ksmedia-_kscamera_profile_concurrencyinfo.md) structures in the **Concurrency** array.

For Windows 10 this must be less than or equal 1.

A value of 0 with **Concurrency** set to **NULL**, indicates this profile is non-concurrent.

### -field Camera.Concurrency

An array of **KSCAMERA_PROFILE_CONCURRENCYINFO** structures describing the concurrency support for this profile.

If **CountOfConcurrency** is 0, this parameter must be **NULL**.

If **CountOfConcurrency** is greater than 0, this parameter must not be **NULL**.
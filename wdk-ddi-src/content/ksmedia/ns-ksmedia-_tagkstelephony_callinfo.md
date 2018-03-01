---
UID: NS:ksmedia._tagKSTELEPHONY_CALLINFO
title: "_tagKSTELEPHONY_CALLINFO"
author: windows-driver-content
description: The KSTELEPHONY_CALLINFO structure specifies the type and state of a phone call for the KSPROPERTY_TELEPHONY_CALLINFO property.
old-location: audio\kstelephony_callinfo.htm
old-project: audio
ms.assetid: B5B89AAC-169B-42B0-8FC8-AB436EFC3579
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSTELEPHONY_CALLINFO, KSTELEPHONY_CALLINFO, KSTELEPHONY_CALLINFO structure [Audio Devices], PKSTELEPHONY_CALLINFO, PKSTELEPHONY_CALLINFO structure pointer [Audio Devices], _tagKSTELEPHONY_CALLINFO, audio.kstelephony_callinfo, ksmedia/KSTELEPHONY_CALLINFO, ksmedia/PKSTELEPHONY_CALLINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
req.target-min-winversvr: Windows Server 2016
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
-	KSTELEPHONY_CALLINFO
product: Windows
targetos: Windows
req.typenames: KSTELEPHONY_CALLINFO, *PKSTELEPHONY_CALLINFO
---

# _tagKSTELEPHONY_CALLINFO structure


## -description


The <b>KSTELEPHONY_CALLINFO</b> structure specifies the type and state of a phone call for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169873">KSPROPERTY_TELEPHONY_CALLINFO</a> property.


## -syntax


````
typedef struct _tagKSTELEPHONY_CALLINFO {
  TELEPHONY_CALLTYPE  CallType;
  TELEPHONY_CALLSTATE CallState;
} KSTELEPHONY_CALLINFO, *PKSTELEPHONY_CALLINFO;
````


## -struct-fields




### -field CallType

Specifies the type of phone call (circuit-switched, LTE packet-switched, or WLAN packet-switched).


### -field CallState

Specifies the state of the phone call.


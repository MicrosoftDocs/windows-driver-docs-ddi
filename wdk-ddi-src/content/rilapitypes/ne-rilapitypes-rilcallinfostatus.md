---
UID: NE:rilapitypes.RILCALLINFOSTATUS
title: RILCALLINFOSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfostatus_2.htm
old-project: netvista
ms.assetid: 16ecddf7-6c79-4e95-957d-19f27c3e3cf5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_CPISTAT_CONNECTED, rilapitypes/RIL_CPISTAT_HANDOVER, RILCALLINFOSTATUS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CPISTAT_ONHOLD, RIL_CPISTAT_NEW_OUTGOING, rilapitypes/RILCALLINFOSTATUS, RIL_CPISTAT_CONNECTED, RIL_CPISTAT_ONHOLD, rilapitypes/RIL_CPISTAT_DISCONNECTED, rilapitypes/RIL_CPISTAT_MAX, rilapitypes/RIL_CPISTAT_NEW_INCOMING, RILCALLINFOSTATUS, RIL_CPISTAT_DISCONNECTED, RIL_CPISTAT_NEW_INCOMING, RIL_CPISTAT_MEDIA, rilapitypes/RIL_CPISTAT_MEDIA, rilapitypes/RIL_CPISTAT_NEW_OUTGOING, RIL_CPISTAT_MAX, netvista.rilcallinfostatus_2, RIL_CPISTAT_HANDOVER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILCALLINFOSTATUS
product: Windows
targetos: Windows
req.typenames: RILCALLINFOSTATUS
req.product: Windows 10 or later.
---

# RILCALLINFOSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLINFOSTATUS { 
  RIL_CPISTAT_NEW_OUTGOING,
  RIL_CPISTAT_NEW_INCOMING,
  RIL_CPISTAT_CONNECTED,
  RIL_CPISTAT_DISCONNECTED,
  RIL_CPISTAT_ONHOLD,
  RIL_CPISTAT_MEDIA,
  RIL_CPISTAT_HANDOVER,
  RIL_CPISTAT_MAX
} RILCALLINFOSTATUS;
````


## -enum-fields




### -field RIL_CPISTAT_UNKNOWN



### -field RIL_CPISTAT_NEW_OUTGOING



### -field RIL_CPISTAT_NEW_INCOMING



### -field RIL_CPISTAT_CONNECTED



### -field RIL_CPISTAT_DISCONNECTED



### -field RIL_CPISTAT_ONHOLD



### -field RIL_CPISTAT_MEDIA



### -field RIL_CPISTAT_HANDOVER



### -field RIL_CPISTAT_MAX



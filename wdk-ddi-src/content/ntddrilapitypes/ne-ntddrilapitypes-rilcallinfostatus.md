---
UID: NE:ntddrilapitypes.RILCALLINFOSTATUS
title: RILCALLINFOSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfostatus.htm
old-project: netvista
ms.assetid: 0f5806e8-a7be-4703-8847-abea2d0cb2e8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_CPISTAT_CONNECTED, ntddrilapitypes/RIL_CPISTAT_MAX, RIL_CPISTAT_NEW_INCOMING, ntddrilapitypes/RIL_CPISTAT_NEW_INCOMING, ntddrilapitypes/RIL_CPISTAT_HANDOVER, ntddrilapitypes/RILCALLINFOSTATUS, netvista.rilcallinfostatus, RIL_CPISTAT_MAX, ntddrilapitypes/RIL_CPISTAT_NEW_OUTGOING, ntddrilapitypes/RIL_CPISTAT_ONHOLD, ntddrilapitypes/RIL_CPISTAT_MEDIA, RIL_CPISTAT_HANDOVER, RILCALLINFOSTATUS, RILCALLINFOSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_CPISTAT_MEDIA, RIL_CPISTAT_CONNECTED, RIL_CPISTAT_NEW_OUTGOING, RIL_CPISTAT_DISCONNECTED, ntddrilapitypes/RIL_CPISTAT_DISCONNECTED, RIL_CPISTAT_ONHOLD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILCALLINFOSTATUS
product: Windows
targetos: Windows
req.typenames: RILCALLINFOSTATUS
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



#### - RIL_CPISTAT_NEW_OUTGOING



#### - RIL_CPISTAT_NEW_INCOMING



#### - RIL_CPISTAT_CONNECTED



#### - RIL_CPISTAT_DISCONNECTED



#### - RIL_CPISTAT_ONHOLD



#### - RIL_CPISTAT_MEDIA



#### - RIL_CPISTAT_HANDOVER



#### - RIL_CPISTAT_MAX



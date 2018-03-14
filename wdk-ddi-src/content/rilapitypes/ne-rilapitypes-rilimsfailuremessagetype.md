---
UID: NE:rilapitypes.RILIMSFAILUREMESSAGETYPE
title: RILIMSFAILUREMESSAGETYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsfailuremessagetype.htm
old-project: netvista
ms.assetid: e40241e6-90ee-4bbb-8fde-f52ffd838c1f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILIMSFAILUREMESSAGETYPE, RILIMSFAILUREMESSAGETYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSFAILUREMESSAGETYPE_INCALL, RIL_IMSFAILUREMESSAGETYPE_MAX, RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE, netvista.rilimsfailuremessagetype, ntddrilapitypes/RILIMSFAILUREMESSAGETYPE, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_INCALL, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_MAX, ntddrilapitypes/RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILIMSFAILUREMESSAGETYPE
product: Windows
targetos: Windows
req.typenames: RILIMSFAILUREMESSAGETYPE
req.product: Windows 10 or later.
---

# RILIMSFAILUREMESSAGETYPE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILIMSFAILUREMESSAGETYPE { 
  RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE,
  RIL_IMSFAILUREMESSAGETYPE_INCALL,
  RIL_IMSFAILUREMESSAGETYPE_MAX
} RILIMSFAILUREMESSAGETYPE;
````


## -enum-fields




### -field RIL_IMSFAILUREMESSAGETYPE_REGISTER


### -field RIL_IMSFAILUREMESSAGETYPE_SUBSCRIBE


### -field RIL_IMSFAILUREMESSAGETYPE_INCALL


### -field RIL_IMSFAILUREMESSAGETYPE_MAX


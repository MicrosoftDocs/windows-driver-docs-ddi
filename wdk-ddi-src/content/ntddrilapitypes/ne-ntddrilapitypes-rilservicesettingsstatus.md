---
UID: NE:ntddrilapitypes.RILSERVICESETTINGSSTATUS
title: RILSERVICESETTINGSSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilservicesettingsstatus.htm
old-project: netvista
ms.assetid: 69340d17-900f-4c46-aafb-866edcb03d77
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SVCSTAT_MAX, RIL_SVCSTAT_DISABLED, ntddrilapitypes/RILSERVICESETTINGSSTATUS, RILSERVICESETTINGSSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_SVCSTAT_DEFAULT, netvista.rilservicesettingsstatus, ntddrilapitypes/RIL_SVCSTAT_MAX, RIL_SVCSTAT_ENABLED, RILSERVICESETTINGSSTATUS, ntddrilapitypes/RIL_SVCSTAT_DEFAULT, ntddrilapitypes/RIL_SVCSTAT_DISABLED, ntddrilapitypes/RIL_SVCSTAT_ENABLED
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
-	RILSERVICESETTINGSSTATUS
product: Windows
targetos: Windows
req.typenames: RILSERVICESETTINGSSTATUS
---

# RILSERVICESETTINGSSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILSERVICESETTINGSSTATUS { 
  RIL_SVCSTAT_DISABLED,
  RIL_SVCSTAT_ENABLED,
  RIL_SVCSTAT_DEFAULT,
  RIL_SVCSTAT_MAX
} RILSERVICESETTINGSSTATUS;
````


## -enum-fields




### -field RIL_SVCSTAT_UNKNOWN



### -field RIL_SVCSTAT_DISABLED



### -field RIL_SVCSTAT_ENABLED



### -field RIL_SVCSTAT_DEFAULT



### -field RIL_SVCSTAT_MAX



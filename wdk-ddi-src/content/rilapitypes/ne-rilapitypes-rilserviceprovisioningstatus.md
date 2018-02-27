---
UID: NE:rilapitypes.RILSERVICEPROVISIONINGSTATUS
title: RILSERVICEPROVISIONINGSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilserviceprovisioningstatus_2.htm
old-project: netvista
ms.assetid: 044d89f7-6167-4e85-b4b4-d706a1499480
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSERVICEPROVISIONINGSTATUS, RILSERVICEPROVISIONINGSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_SVCPROV_MAX, RIL_SVCPROV_NOTPROVISIONED, RIL_SVCPROV_PROVISIONED, RIL_SVCPROV_TEMPMODEALLOWED, RIL_SVCPROV_TEMPMODERESTRICTED, netvista.rilserviceprovisioningstatus_2, rilapitypes/RILSERVICEPROVISIONINGSTATUS, rilapitypes/RIL_SVCPROV_MAX, rilapitypes/RIL_SVCPROV_NOTPROVISIONED, rilapitypes/RIL_SVCPROV_PROVISIONED, rilapitypes/RIL_SVCPROV_TEMPMODEALLOWED, rilapitypes/RIL_SVCPROV_TEMPMODERESTRICTED
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
-	RILSERVICEPROVISIONINGSTATUS
product: Windows
targetos: Windows
req.typenames: RILSERVICEPROVISIONINGSTATUS
req.product: Windows 10 or later.
---

# RILSERVICEPROVISIONINGSTATUS enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILSERVICEPROVISIONINGSTATUS { 
  RIL_SVCPROV_NOTPROVISIONED,
  RIL_SVCPROV_PROVISIONED,
  RIL_SVCPROV_TEMPMODERESTRICTED,
  RIL_SVCPROV_TEMPMODEALLOWED,
  RIL_SVCPROV_MAX
} RILSERVICEPROVISIONINGSTATUS;
````


## -enum-fields




### -field RIL_SVCPROV_UNKNOWN


### -field RIL_SVCPROV_NOTPROVISIONED


### -field RIL_SVCPROV_PROVISIONED


### -field RIL_SVCPROV_TEMPMODERESTRICTED


### -field RIL_SVCPROV_TEMPMODEALLOWED


### -field RIL_SVCPROV_MAX


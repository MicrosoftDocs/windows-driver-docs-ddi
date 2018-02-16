---
UID: NE:ntddrilapitypes.RILSERVICEPROVISIONINGSTATUS
title: RILSERVICEPROVISIONINGSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilserviceprovisioningstatus.htm
old-project: netvista
ms.assetid: 2f611dff-56b5-406f-8f67-cd3744caa1b5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_SVCPROV_NOTPROVISIONED, netvista.rilserviceprovisioningstatus, ntddrilapitypes/RIL_SVCPROV_TEMPMODERESTRICTED, RIL_SVCPROV_TEMPMODEALLOWED, RILSERVICEPROVISIONINGSTATUS, ntddrilapitypes/RILSERVICEPROVISIONINGSTATUS, RIL_SVCPROV_TEMPMODERESTRICTED, ntddrilapitypes/RIL_SVCPROV_PROVISIONED, RIL_SVCPROV_PROVISIONED, ntddrilapitypes/RIL_SVCPROV_NOTPROVISIONED, ntddrilapitypes/RIL_SVCPROV_TEMPMODEALLOWED, ntddrilapitypes/RIL_SVCPROV_MAX, RILSERVICEPROVISIONINGSTATUS enumeration [Network Drivers Starting with Windows Vista], RIL_SVCPROV_MAX
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
-	RILSERVICEPROVISIONINGSTATUS
product: Windows
targetos: Windows
req.typenames: RILSERVICEPROVISIONINGSTATUS
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


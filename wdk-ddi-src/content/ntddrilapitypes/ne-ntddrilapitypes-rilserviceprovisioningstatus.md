---
UID: NE:ntddrilapitypes.RILSERVICEPROVISIONINGSTATUS
title: RILSERVICEPROVISIONINGSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilserviceprovisioningstatus.htm
old-project: netvista
ms.assetid: 2f611dff-56b5-406f-8f67-cd3744caa1b5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSERVICEPROVISIONINGSTATUS, RILSERVICEPROVISIONINGSTATUS
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
req.alt-api: RILSERVICEPROVISIONINGSTATUS
req.alt-loc: ntddrilapitypes.h
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

### -field RIL_SVCPROV_NOTPROVISIONED


### -field RIL_SVCPROV_PROVISIONED


### -field RIL_SVCPROV_TEMPMODERESTRICTED


### -field RIL_SVCPROV_TEMPMODEALLOWED


### -field RIL_SVCPROV_MAX


## -remarks

---
UID: NE:ntddrilapitypes.RILCALLINFODISCONNECTREASON
title: RILCALLINFODISCONNECTREASON
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodisconnectreason.htm
old-project: netvista
ms.assetid: 2e339b56-9130-4459-8ccd-171f721ae83e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_DISCREASON_RADIOFADE, netvista.rilcallinfodisconnectreason, RIL_DISCREASON_EMERGENCYFAILOVER, ntddrilapitypes/RIL_DISCREASON_BUSY, ntddrilapitypes/RIL_DISCREASON_MAX, RIL_DISCREASON_BUSY, RIL_DISCREASON_OTHEREXECUTORBUSY, ntddrilapitypes/RIL_DISCREASON_EMERGENCYFAILOVER, RIL_DISCREASON_NETWORKERROR, RIL_DISCREASON_CONGESTION, ntddrilapitypes/RIL_DISCREASON_OTHEREXECUTORBUSY, ntddrilapitypes/RIL_DISCREASON_HANDOVER_MERGE, ntddrilapitypes/RIL_DISCREASON_NETWORKERROR, ntddrilapitypes/RILCALLINFODISCONNECTREASON, RIL_DISCREASON_EMERGENCYONLY, RIL_DISCREASON_RADIOFADE, RIL_DISCREASON_HANDOVER_MERGE, RILCALLINFODISCONNECTREASON enumeration [Network Drivers Starting with Windows Vista], RILCALLINFODISCONNECTREASON, RIL_DISCREASON_NOSERVICE, ntddrilapitypes/RIL_DISCREASON_NOSERVICE, RIL_DISCREASON_MAX, ntddrilapitypes/RIL_DISCREASON_EMERGENCYONLY, ntddrilapitypes/RIL_DISCREASON_CONGESTION
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
-	RILCALLINFODISCONNECTREASON
product: Windows
targetos: Windows
req.typenames: RILCALLINFODISCONNECTREASON
---

# RILCALLINFODISCONNECTREASON enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILCALLINFODISCONNECTREASON { 
  RIL_DISCREASON_BUSY,
  RIL_DISCREASON_NETWORKERROR,
  RIL_DISCREASON_RADIOFADE,
  RIL_DISCREASON_CONGESTION,
  RIL_DISCREASON_EMERGENCYONLY,
  RIL_DISCREASON_NOSERVICE,
  RIL_DISCREASON_OTHEREXECUTORBUSY,
  RIL_DISCREASON_EMERGENCYFAILOVER,
  RIL_DISCREASON_HANDOVER_MERGE,
  RIL_DISCREASON_MAX
} RILCALLINFODISCONNECTREASON;
````


## -enum-fields




### -field RIL_DISCREASON_NULL



### -field RIL_DISCREASON_BUSY



### -field RIL_DISCREASON_NETWORKERROR



### -field RIL_DISCREASON_RADIOFADE



### -field RIL_DISCREASON_CONGESTION



### -field RIL_DISCREASON_EMERGENCYONLY



### -field RIL_DISCREASON_NOSERVICE



### -field RIL_DISCREASON_OTHEREXECUTORBUSY



### -field RIL_DISCREASON_EMERGENCYFAILOVER



### -field RIL_DISCREASON_HANDOVER_MERGE



### -field RIL_DISCREASON_MAX



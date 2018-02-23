---
UID: NE:ntddrilapitypes.RILEMERGENCYMODECONTROLPARAMSCONTROL
title: RILEMERGENCYMODECONTROLPARAMSCONTROL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencymodecontrolparamscontrol.htm
old-project: netvista
ms.assetid: ac5a2ae3-3fdc-463f-96df-22b441e38724
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilemergencymodecontrolparamscontrol, ntddrilapitypes/RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE, RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE, RIL_EMC_MAX, RILEMERGENCYMODECONTROLPARAMSCONTROL, RILEMERGENCYMODECONTROLPARAMSCONTROL enumeration [Network Drivers Starting with Windows Vista], RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE, ntddrilapitypes/RIL_EMC_MAX, ntddrilapitypes/RILEMERGENCYMODECONTROLPARAMSCONTROL, ntddrilapitypes/RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE
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
-	RILEMERGENCYMODECONTROLPARAMSCONTROL
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYMODECONTROLPARAMSCONTROL
---

# RILEMERGENCYMODECONTROLPARAMSCONTROL enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILEMERGENCYMODECONTROLPARAMSCONTROL { 
  RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE,
  RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE,
  RIL_EMC_MAX
} RILEMERGENCYMODECONTROLPARAMSCONTROL;
````


## -enum-fields




### -field RIL_EMC_EXIT_CDMA_ECBM


### -field RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE


### -field RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE


### -field RIL_EMC_MAX


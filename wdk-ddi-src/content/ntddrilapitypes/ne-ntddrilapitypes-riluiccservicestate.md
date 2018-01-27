---
UID: NE:ntddrilapitypes.RILUICCSERVICESTATE
title: RILUICCSERVICESTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccservicestate.htm
old-project: netvista
ms.assetid: 01d64333-3f49-45e1-bd2b-dda0aeb6a083
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCSERVICESTATE, ntddrilapitypes/RIL_UICCSERVICESTATE_DISABLED, RIL_UICCSERVICESTATE_ENABLED, RIL_UICCSERVICESTATE_DISABLED, netvista.riluiccservicestate, ntddrilapitypes/RIL_UICCSERVICESTATE_ENABLED, ntddrilapitypes/RIL_UICCSERVICESTATE_MAX, RIL_UICCSERVICESTATE_MAX, RILUICCSERVICESTATE enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILUICCSERVICESTATE
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
-	RILUICCSERVICESTATE
product: Windows
targetos: Windows
req.typenames: RILUICCSERVICESTATE
---

# RILUICCSERVICESTATE enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILUICCSERVICESTATE { 
  RIL_UICCSERVICESTATE_DISABLED,
  RIL_UICCSERVICESTATE_ENABLED,
  RIL_UICCSERVICESTATE_MAX
} RILUICCSERVICESTATE;
````


## -enum-fields




### -field RIL_UICCSERVICESTATE_NOTAVAILABLE



### -field RIL_UICCSERVICESTATE_DISABLED



### -field RIL_UICCSERVICESTATE_ENABLED



### -field RIL_UICCSERVICESTATE_MAX



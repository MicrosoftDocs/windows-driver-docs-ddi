---
UID: NS:rilapitypes.RILUICCAPPPERSOCHECKSTATUS
title: RILUICCAPPPERSOCHECKSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccapppersocheckstatus_2.htm
old-project: netvista
ms.assetid: 8e51ae9a-4670-4de1-bfca-bef8cb0c9cc9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCAPPPERSOCHECKSTATUS structure [Network Drivers Starting with Windows Vista], netvista.riluiccapppersocheckstatus_2, rilapitypes/RILUICCAPPPERSOCHECKSTATUS, *LPRILUICCAPPPERSOCHECKSTATUS, RILUICCAPPPERSOCHECKSTATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.lib: 
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
-	RILUICCAPPPERSOCHECKSTATUS
product: Windows
targetos: Windows
req.typenames: RILUICCAPPPERSOCHECKSTATUS, *LPRILUICCAPPPERSOCHECKSTATUS
req.product: Windows 10 or later.
---

# RILUICCAPPPERSOCHECKSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCAPPPERSOCHECKSTATUS {
  DWORD                            cbSize;
  DWORD                            dwParams;
  HUICCAPP                         hUiccApp;
  DWORD                            dwPersoFeature;
  RILUICCAPPPERSOCHECKSTATUSSTATE  dwPersoCheckState;
} RILUICCAPPPERSOCHECKSTATUS, RILUICCAPPPERSOCHECKSTATUS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field hUiccApp


### -field dwPersoFeature


### -field dwPersoCheckState


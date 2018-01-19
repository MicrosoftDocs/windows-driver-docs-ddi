---
UID: NS:ntddrilapitypes.RILUICCAPPPERSOCHECKSTATUS
title: RILUICCAPPPERSOCHECKSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccapppersocheckstatus.htm
old-project: netvista
ms.assetid: 6438f692-75b0-4a41-a2f9-68b0fe3f23cf
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCAPPPERSOCHECKSTATUS, *LPRILUICCAPPPERSOCHECKSTATUS, RILUICCAPPPERSOCHECKSTATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCAPPPERSOCHECKSTATUS
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
req.typenames: *LPRILUICCAPPPERSOCHECKSTATUS, RILUICCAPPPERSOCHECKSTATUS
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


## -remarks

---
UID: NS:ntddrilapitypes.RILSYSTEMSELECTIONPREFS_V2
title: RILSYSTEMSELECTIONPREFS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v2.htm
old-project: netvista
ms.assetid: 0734fac3-9327-4765-a50b-57be45ce2817
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilsystemselectionprefs_v2, RILSYSTEMSELECTIONPREFS, ntddrilapitypes/RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS"
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
-	RILSYSTEMSELECTIONPREFS_V2
product: Windows
targetos: Windows
req.typenames: "*LPRILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS_V2"
---

# RILSYSTEMSELECTIONPREFS_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSYSTEMSELECTIONPREFS_V2 {
  DWORD                               cbSize;
  DWORD                               dwParams;
  DWORD                               dwExecutor;
  DWORD                               dwSystemTypes;
  RILSYSTEMSELECTIONPREFSMODE         dwMode;
  RILOPERATORNAMES                    plmnInfo;
  RILSYSTEMSELECTIONPREFSROAMINGMODE  dwRoamingMode;
  DWORD                               dwAcquisitionOrderSize;
  DWORD [16]                          AcquisitionOrder;
} RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2;
````


## -struct-fields




#### - cbSize



#### - dwParams



#### - dwExecutor



#### - dwSystemTypes



#### - dwMode



#### - plmnInfo



#### - dwRoamingMode



#### - dwAcquisitionOrderSize



#### - AcquisitionOrder



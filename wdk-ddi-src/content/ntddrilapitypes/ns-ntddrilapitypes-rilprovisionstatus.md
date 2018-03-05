---
UID: NS:ntddrilapitypes.RILPROVISIONSTATUS
title: RILPROVISIONSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilprovisionstatus.htm
old-project: netvista
ms.assetid: 5295f07d-9800-47f0-a827-515fcdad04eb
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILPROVISIONSTATUS, RILPROVISIONSTATUS, RILPROVISIONSTATUS structure [Network Drivers Starting with Windows Vista], netvista.rilprovisionstatus, ntddrilapitypes/RILPROVISIONSTATUS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILPROVISIONSTATUS
product: Windows
targetos: Windows
req.typenames: RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS
---

# RILPROVISIONSTATUS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILPROVISIONSTATUS {
  DWORD                              cbSize;
  DWORD                              dwExecutor;
  RILPROVISIONSTATUSPROVISIONSTATUS  dwProvisionStatus;
} RILPROVISIONSTATUS, RILPROVISIONSTATUS;
````


## -struct-fields




### -field cbSize


### -field dwExecutor


### -field dwProvisionStatus


---
UID: NS:rilapitypes.RILPROVISIONSTATUS
title: RILPROVISIONSTATUS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilprovisionstatus_2.htm
old-project: netvista
ms.assetid: 59568338-6718-4f3e-bcf6-cd284e68e6af
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilprovisionstatus_2, RILPROVISIONSTATUS structure [Network Drivers Starting with Windows Vista], RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS, rilapitypes/RILPROVISIONSTATUS
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
-	RILPROVISIONSTATUS
product: Windows
targetos: Windows
req.typenames: *LPRILPROVISIONSTATUS, RILPROVISIONSTATUS
req.product: Windows 10 or later.
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



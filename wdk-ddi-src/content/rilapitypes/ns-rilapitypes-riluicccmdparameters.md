---
UID: NS:rilapitypes.RILUICCCMDPARAMETERS
title: RILUICCCMDPARAMETERS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccmdparameters_2.htm
old-project: netvista
ms.assetid: 8ebffcdc-672b-4cfd-9ff2-a911b7c4dde5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCCMDPARAMETERS structure [Network Drivers Starting with Windows Vista], *LPRILUICCCMDPARAMETERS, rilapitypes/RILUICCCMDPARAMETERS, netvista.riluicccmdparameters_2, RILUICCCMDPARAMETERS
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
-	RILUICCCMDPARAMETERS
product: Windows
targetos: Windows
req.typenames: RILUICCCMDPARAMETERS, *LPRILUICCCMDPARAMETERS
req.product: Windows 10 or later.
---

# RILUICCCMDPARAMETERS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCCMDPARAMETERS {
  DWORD            cbSize;
  DWORD            dwParams;
  RILUICCFILEPATH  filePath;
  DWORD            dwParameter1;
  DWORD            dwParameter2;
  DWORD            dwParameter3;
} RILUICCCMDPARAMETERS, RILUICCCMDPARAMETERS;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field filePath


### -field dwParameter1


### -field dwParameter2


### -field dwParameter3


---
UID: NS:rilapitypes.RILUICCFILEPATH
title: RILUICCFILEPATH
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluiccfilepath_2.htm
old-project: netvista
ms.assetid: d0321907-0a3c-43cc-97f1-a3a7e9b84311
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILUICCFILEPATH, *LPRILUICCFILEPATH, RILUICCFILEPATH structure [Network Drivers Starting with Windows Vista], netvista.riluiccfilepath_2, rilapitypes/RILUICCFILEPATH
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
-	RILUICCFILEPATH
product: Windows
targetos: Windows
req.typenames: RILUICCFILEPATH, *LPRILUICCFILEPATH
req.product: Windows 10 or later.
---

# RILUICCFILEPATH structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCFILEPATH {
  HUICCAPP                  hUiccApp;
  DWORD                     dwFilePathLen;
  WORD [MAXLENGTH_UICCPATH] wFilePath;
} RILUICCFILEPATH, RILUICCFILEPATH;
````


## -struct-fields




### -field hUiccApp



### -field dwFilePathLen



### -field wFilePath



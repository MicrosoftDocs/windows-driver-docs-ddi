---
UID: NS:ntddrilapitypes.RILSENDRESTRICTEDUICCCMDPARAMS
title: RILSENDRESTRICTEDUICCCMDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendrestricteduicccmdparams.htm
old-project: netvista
ms.assetid: 22c7ae24-c2dc-46d6-b3c2-b908ad6d181c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS structure [Network Drivers Starting with Windows Vista], netvista.rilsendrestricteduicccmdparams, ntddrilapitypes/RILSENDRESTRICTEDUICCCMDPARAMS"
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
-	RILSENDRESTRICTEDUICCCMDPARAMS
product: Windows
targetos: Windows
req.typenames: RILSENDRESTRICTEDUICCCMDPARAMS, *LPRILSENDRESTRICTEDUICCCMDPARAMS
---

# RILSENDRESTRICTEDUICCCMDPARAMS structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSENDRESTRICTEDUICCCMDPARAMS {
  DWORD                  cbSize;
  RILUICCCOMMAND         dwCommand;
  RILUICCCMDPARAMETERS   rscpParameters;
  BOOL                   fHasLockVerification;
  RILUICCLOCKCREDENTIAL  lockVerification;
  DWORD                  dwDataSize;
  BYTE [1]               pbData;
} RILSENDRESTRICTEDUICCCMDPARAMS, RILSENDRESTRICTEDUICCCMDPARAMS;
````


## -struct-fields




### -field cbSize


### -field dwCommand


### -field rscpParameters


### -field fHasLockVerification


### -field lockVerification


### -field dwDataSize


### -field pbData


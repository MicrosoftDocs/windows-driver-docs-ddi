---
UID: NE:prdrvcom.tagSHIMOPTS
title: tagSHIMOPTS
author: windows-driver-content
description: "."
old-location: print\shimopts.htm
old-project: print
ms.assetid: 7A00F51A-E8EB-4D8F-B130-08834BF741C6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: prdrvcom/PTSHIM_NOSNAPSHOT, print.shimopts, prdrvcom/SHIMOPTS, SHIMOPTS enumeration [Print Devices], prdrvcom/PSHIMOPTS, SHIMOPTS, PSHIMOPTS, PTSHIM_NOSNAPSHOT, *PSHIMOPTS, prdrvcom/PTSHIM_DEFAULT, PTSHIM_DEFAULT, PSHIMOPTS enumeration pointer [Print Devices], tagSHIMOPTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: prdrvcom.h
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
-	Prdrvcom.h
apiname:
-	SHIMOPTS
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---

# tagSHIMOPTS enumeration


## -description





## -syntax


````
typedef enum tagSHIMOPTS { 
  PTSHIM_DEFAULT     = 0,
  PTSHIM_NOSNAPSHOT  = 0x1
} SHIMOPTS, *PSHIMOPTS;
````


## -enum-fields




#### - PTSHIM_DEFAULT



#### - PTSHIM_NOSNAPSHOT



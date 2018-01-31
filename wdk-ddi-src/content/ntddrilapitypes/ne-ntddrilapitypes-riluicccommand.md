---
UID: NE:ntddrilapitypes.RILUICCCOMMAND
title: RILUICCCOMMAND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccommand.htm
old-project: netvista
ms.assetid: 1c2ded31-9d2d-46e4-a23f-a48528fd448f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_UICCCMD_UPDATEBINARY, ntddrilapitypes/RIL_UICCCMD_MAX, RIL_UICCCMD_UPDATERECORD, RILUICCCOMMAND enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_UICCCMD_READRECORD, RILUICCCOMMAND, ntddrilapitypes/RIL_UICCCMD_UPDATERECORD, netvista.riluicccommand, ntddrilapitypes/RILUICCCOMMAND, RIL_UICCCMD_READRECORD, RIL_UICCCMD_UPDATEBINARY, RIL_UICCCMD_MAX
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
-	RILUICCCOMMAND
product: Windows
targetos: Windows
req.typenames: RILUICCCOMMAND
---

# RILUICCCOMMAND enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef enum _RILUICCCOMMAND { 
  RIL_UICCCMD_READRECORD,
  RIL_UICCCMD_UPDATEBINARY,
  RIL_UICCCMD_UPDATERECORD,
  RIL_UICCCMD_MAX
} RILUICCCOMMAND;
````


## -enum-fields




### -field RIL_UICCCMD_READBINARY



#### - RIL_UICCCMD_READRECORD



#### - RIL_UICCCMD_UPDATEBINARY



#### - RIL_UICCCMD_UPDATERECORD



#### - RIL_UICCCMD_MAX



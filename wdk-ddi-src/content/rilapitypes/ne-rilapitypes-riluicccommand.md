---
UID: NE:rilapitypes.RILUICCCOMMAND
title: RILUICCCOMMAND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccommand_2.htm
old-project: netvista
ms.assetid: 13861810-91a6-4027-81a0-297b049e3ee4
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_UICCCMD_MAX, netvista.riluicccommand_2, RILUICCCOMMAND, rilapitypes/RILUICCCOMMAND, rilapitypes/RIL_UICCCMD_UPDATEBINARY, rilapitypes/RIL_UICCCMD_MAX, RILUICCCOMMAND enumeration [Network Drivers Starting with Windows Vista], RIL_UICCCMD_READRECORD, RIL_UICCCMD_UPDATEBINARY, rilapitypes/RIL_UICCCMD_UPDATERECORD, RIL_UICCCMD_UPDATERECORD, rilapitypes/RIL_UICCCMD_READRECORD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILUICCCOMMAND
product: Windows
targetos: Windows
req.typenames: RILUICCCOMMAND
req.product: Windows 10 or later.
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



### -field RIL_UICCCMD_READRECORD



### -field RIL_UICCCMD_UPDATEBINARY



### -field RIL_UICCCMD_UPDATERECORD



### -field RIL_UICCCMD_MAX



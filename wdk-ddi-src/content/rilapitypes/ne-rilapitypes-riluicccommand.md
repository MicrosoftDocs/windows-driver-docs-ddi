---
UID: NE:rilapitypes.RILUICCCOMMAND
title: RILUICCCOMMAND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccommand_2.htm
old-project: netvista
ms.assetid: 13861810-91a6-4027-81a0-297b049e3ee4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILUICCCOMMAND, RILUICCCOMMAND enumeration [Network Drivers Starting with Windows Vista], RIL_UICCCMD_MAX, RIL_UICCCMD_READRECORD, RIL_UICCCMD_UPDATEBINARY, RIL_UICCCMD_UPDATERECORD, netvista.riluicccommand_2, rilapitypes/RILUICCCOMMAND, rilapitypes/RIL_UICCCMD_MAX, rilapitypes/RIL_UICCCMD_READRECORD, rilapitypes/RIL_UICCCMD_UPDATEBINARY, rilapitypes/RIL_UICCCMD_UPDATERECORD
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
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


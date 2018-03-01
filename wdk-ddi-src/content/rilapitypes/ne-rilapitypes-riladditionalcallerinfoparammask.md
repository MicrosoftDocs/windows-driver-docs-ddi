---
UID: NE:rilapitypes.RILADDITIONALCALLERINFOPARAMMASK
title: RILADDITIONALCALLERINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riladditionalcallerinfoparammask_2.htm
old-project: netvista
ms.assetid: 1de91e12-1f8c-48fa-85e4-c3cb061fce78
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILADDITIONALCALLERINFOPARAMMASK, RILADDITIONALCALLERINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_ADDTLCI_ALL, RIL_PARAM_ADDTLCI_CALLERINFO, RIL_PARAM_ADDTLCI_CALLERINFOLENGTH, RIL_PARAM_ADDTLCI_CALLID, netvista.riladditionalcallerinfoparammask_2, rilapitypes/RILADDITIONALCALLERINFOPARAMMASK, rilapitypes/RIL_PARAM_ADDTLCI_ALL, rilapitypes/RIL_PARAM_ADDTLCI_CALLERINFO, rilapitypes/RIL_PARAM_ADDTLCI_CALLERINFOLENGTH, rilapitypes/RIL_PARAM_ADDTLCI_CALLID
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
-	RILADDITIONALCALLERINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILADDITIONALCALLERINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILADDITIONALCALLERINFOPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILADDITIONALCALLERINFOPARAMMASK { 
  RIL_PARAM_ADDTLCI_CALLID,
  RIL_PARAM_ADDTLCI_CALLERINFOLENGTH,
  RIL_PARAM_ADDTLCI_CALLERINFO,
  RIL_PARAM_ADDTLCI_ALL
} RILADDITIONALCALLERINFOPARAMMASK;
````


## -enum-fields




### -field RIL_PARAM_ADDTLCI_EXECUTOR


### -field RIL_PARAM_ADDTLCI_CALLID


### -field RIL_PARAM_ADDTLCI_CALLERINFOLENGTH


### -field RIL_PARAM_ADDTLCI_CALLERINFO


### -field RIL_PARAM_ADDTLCI_ALL


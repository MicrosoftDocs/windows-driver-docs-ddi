---
UID: NF:rilapi.RIL_SetEquipmentState
title: RIL_SetEquipmentState function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_setequipmentstate.htm
old-project: netvista
ms.assetid: 52b76027-5562-403b-9993-40d3d9a33e35
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapi/RIL_SetEquipmentState, netvista.ril_setequipmentstate, RIL_SetEquipmentState method [Network Drivers Starting with Windows Vista], RIL_SetEquipmentState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	rilapi.h
apiname:
-	RIL_SetEquipmentState
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SetEquipmentState function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_SetEquipmentState(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwEquipmentState
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwEquipmentState


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




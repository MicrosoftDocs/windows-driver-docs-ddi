---
UID: NC:bthddi.PFNBTH_FREE_BRB
title: PFNBTH_FREE_BRB (bthddi.h)
description: The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb.
old-location: bltooth\bthfreebrb.htm
tech.root: bltooth
ms.assetid: fc24cdaf-0695-4e10-82be-a7f7a916f550
ms.date: 04/27/2018
ms.keywords: BthFreeBrb, BthFreeBrb callback function [Bluetooth Devices], PFNBTH_FREE_BRB, PFNBTH_FREE_BRB callback, bltooth.bthfreebrb, bth_funcs_434cd24f-2604-4526-ac74-14a151365658.xml, bthddi/BthFreeBrb
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- bthddi.h
api_name:
- BthFreeBrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNBTH_FREE_BRB callback function


## -description


The 
  <i>BthFreeBrb</i> function frees a Bluetooth request block (BRB) that was allocated previously with 
  <i>BthAllocateBrb</i>.


## -parameters




### -param pBrb [in]

Pointer to the BRB to free.


## -returns



None.




## -remarks



Profile drivers obtain a pointer to the 
    <i>BthFreeBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="https://msdn.microsoft.com/56db29cd-26ab-4262-9b9f-40d46372ffe9">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.




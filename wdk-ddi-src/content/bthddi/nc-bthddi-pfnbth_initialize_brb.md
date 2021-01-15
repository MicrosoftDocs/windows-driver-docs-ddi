---
UID: NC:bthddi.PFNBTH_INITIALIZE_BRB
title: PFNBTH_INITIALIZE_BRB (bthddi.h)
description: The BthInitializeBrb function initializes a Bluetooth request block (BRB) allocated on the local stack.
old-location: bltooth\bthinitializebrb.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["PFNBTH_INITIALIZE_BRB callback function"]
ms.keywords: BthInitializeBrb, BthInitializeBrb callback function [Bluetooth Devices], PFNBTH_INITIALIZE_BRB, PFNBTH_INITIALIZE_BRB callback, bltooth.bthinitializebrb, bth_funcs_11ec7e91-bfca-404f-a029-a3fbb8c56d47.xml, bthddi/BthInitializeBrb
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNBTH_INITIALIZE_BRB
 - bthddi/PFNBTH_INITIALIZE_BRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - bthddi.h
api_name:
 - PFNBTH_INITIALIZE_BRB
---

# PFNBTH_INITIALIZE_BRB callback function


## -description

The 
  <i>BthInitializeBrb</i> function initializes a Bluetooth request block (BRB) allocated on the local
  stack.

## -parameters

### -param pBrb 

[in, out]
Pointer to the BRB to initialize.

### -param brbType 

[in]
Specifies a value from the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_brb_type">BRB_TYPE</a> enumeration to initialize the BRB
     with.

## -remarks

Profile drivers should use 
    <i>BthInitializeBrb</i> for stack based allocations, such as declaring variables at the beginning of a
    function.

It is not necessary to call this function for a BRB that was allocated using 
    <a href="/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a>.

Profile drivers obtain a pointer to the 
    <i>BthInitializeBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="/previous-versions/ff536769(v=vs.85)">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_brb_type">BRB_TYPE</a>



<a href="/windows-hardware/drivers/ddi/bthddi/nc-bthddi-pfnbth_allocate_brb">BthAllocateBrb</a>


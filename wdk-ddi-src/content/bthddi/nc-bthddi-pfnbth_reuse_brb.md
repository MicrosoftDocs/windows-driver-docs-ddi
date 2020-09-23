---
UID: NC:bthddi.PFNBTH_REUSE_BRB
title: PFNBTH_REUSE_BRB (bthddi.h)
description: The BthReuseBrb function reinitializes a Bluetooth request block (BRB) to be reused.
old-location: bltooth\bthreusebrb.htm
tech.root: bltooth
ms.assetid: cdf156a1-1556-441a-ae3d-9a49daf47990
ms.date: 04/27/2018
keywords: ["PFNBTH_REUSE_BRB callback function"]
ms.keywords: BthReuseBrb, BthReuseBrb callback function [Bluetooth Devices], PFNBTH_REUSE_BRB, PFNBTH_REUSE_BRB callback, bltooth.bthreusebrb, bth_funcs_118c4022-448d-4970-ba70-34dcbc488d13.xml, bthddi/BthReuseBrb
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
 - PFNBTH_REUSE_BRB
 - bthddi/PFNBTH_REUSE_BRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - bthddi.h
api_name:
 - BthReuseBrb
---

# PFNBTH_REUSE_BRB callback function


## -description

The 
  <i>BthReuseBrb</i> function reinitializes a Bluetooth request block (BRB) to be reused.

## -parameters

### -param pBrb 

[in, out]
Pointer to the BRB to reuse.

### -param brbType 

[in]
Specifies a value from the 
     <a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_brb_type">BRB_TYPE</a> enumeration to initialize the BRB
     with.

## -remarks

Profile drivers obtain a pointer to the 
    <i>BthReuseBrb</i> function when they query the Bluetooth driver stack for an instance of the
    BTHDDI_PROFILE_DRIVER_INTERFACE driver interface. See 
    <a href="/previous-versions/ff536769(v=vs.85)">Querying for Bluetooth
    Interfaces</a> for more information about querying the Bluetooth driver stack.

## -see-also

<a href="/windows-hardware/drivers/ddi/bthddi/ne-bthddi-_brb_type">BRB_TYPE</a>
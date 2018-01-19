---
UID: NC:bthddi.PFNBTH_FREE_BRB
title: PFNBTH_FREE_BRB
author: windows-driver-content
description: The BthFreeBrb function frees a Bluetooth request block (BRB) that was allocated previously with BthAllocateBrb.
old-location: bltooth\bthfreebrb.htm
old-project: bltooth
ms.assetid: fc24cdaf-0695-4e10-82be-a7f7a916f550
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: IBidiSpl2, IBidiSpl2::UnbindDevice, UnbindDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Desktop
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BthFreeBrb
req.alt-loc: bthddi.h
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
req.typenames: MPEG2_TRANSPORT_STRIDE, *PMPEG2_TRANSPORT_STRIDE
---

# PFNBTH_FREE_BRB callback



## -description
The 
  <i>BthFreeBrb</i> function frees a Bluetooth request block (BRB) that was allocated previously with 
  <i>BthAllocateBrb</i>.



## -prototype

````
PFNBTH_FREE_BRB BthFreeBrb;

VOID BthFreeBrb(
  _In_ PBRB pBrb
)
{ ... }
````


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
    Interfaces</a> for more information about querying the Bluetooth driver stack.</p>
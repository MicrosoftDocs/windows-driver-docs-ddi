---
UID: NF:ndis.NdisMResetMiniport
title: NdisMResetMiniport function (ndis.h)
description: A miniport driver calls the NdisMResetMiniport function to trigger a later reset operation from NDIS.
old-location: netvista\ndismresetminiport.htm
tech.root: netvista
ms.assetid: 614C6E21-00D0-4F57-9E09-D1BAB166BA42
ms.date: 05/02/2018
keywords: ["NdisMResetMiniport function"]
ms.keywords: NdisMResetMiniport, NdisMResetMiniport function [Network Drivers Starting with Windows Vista], ndis/NdisMResetMiniport, netvista.ndismresetminiport
f1_keywords:
 - "ndis/NdisMResetMiniport"
 - "NdisMResetMiniport"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisMResetMiniport
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMResetMiniport function


## -description


A miniport driver calls the <b>NdisMResetMiniport</b> function to trigger a later reset operation from NDIS.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>.


## -remarks



A miniport driver calls <b>NdisMResetMiniport</b> when it determines that the device requires a hardware reset.

As a result, NDIS schedules a work item for calling the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function asynchronously.

<b>NdisMResetMiniport</b> must be called at IRQL <= DISPATCH_LEVEL.




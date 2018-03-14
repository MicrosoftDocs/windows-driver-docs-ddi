---
UID: NF:ndis.NdisMResetMiniport
title: NdisMResetMiniport function
author: windows-driver-content
description: A miniport driver calls the NdisMResetMiniport function to trigger a later reset operation from NDIS.
old-location: netvista\ndismresetminiport.htm
old-project: netvista
ms.assetid: 614C6E21-00D0-4F57-9E09-D1BAB166BA42
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMResetMiniport, NdisMResetMiniport function [Network Drivers Starting with Windows Vista], ndis/NdisMResetMiniport, netvista.ndismresetminiport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMResetMiniport
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMResetMiniport function


## -description


A miniport driver calls the <b>NdisMResetMiniport</b> function to trigger a later reset operation from NDIS.


## -syntax


````
void NdisMResetMiniport(
  _In_ NDIS_HANDLE MiniportAdapterHandle
);
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the <i>MiniportAdapterHandle</i> parameter of <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>.


## -returns



This function does not return a value.




## -remarks



A miniport driver calls <b>NdisMResetMiniport</b> when it determines that the device requires a hardware reset.

As a result, NDIS schedules a work item for calling the miniport driver's <a href="..\ndis\nc-ndis-miniport_reset.md">MiniportResetEx</a> function asynchronously.

<b>NdisMResetMiniport</b> must be called at IRQL &lt;= DISPATCH_LEVEL.




---
UID: NF:rilapi.RIL_OpenUiccLogicalChannel
title: RIL_OpenUiccLogicalChannel function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_openuicclogicalchannel.htm
old-project: netvista
ms.assetid: 8e77d55d-62f5-450c-9d9a-41acfece84c0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RIL_OpenUiccLogicalChannel, RIL_OpenUiccLogicalChannel method [Network Drivers Starting with Windows Vista], netvista.ril_openuicclogicalchannel, rilapi/RIL_OpenUiccLogicalChannel
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapi.h
api_name:
-	RIL_OpenUiccLogicalChannel
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_OpenUiccLogicalChannel function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_OpenUiccLogicalChannel(
   HRIL        hRil,
   LPVOID      lpContext,
   DWORD       dwSlotIndex,
   DWORD       dwChannelGroup,
   DWORD       dwAppIdLength,
   const BYTE  pbAppId,
   DWORD       dwSelectP2Arg
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwSlotIndex


### -param dwChannelGroup


### -param dwAppIdLength


### -param pbAppId


### -param dwSelectP2Arg


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




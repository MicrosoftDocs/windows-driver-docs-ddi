---
UID: NF:rilapi.RIL_GetRadioStateGroups
title: RIL_GetRadioStateGroups function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getradiostategroups.htm
old-project: netvista
ms.assetid: 7143e3a1-f383-4ea8-8e97-d9d7a9089db4
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , G, I, L, R, RIL_GetRadioStateGroups, RIL_GetRadioStateGroups method [Network Drivers Starting with Windows Vista], S, _, a, d, e, i, netvista.ril_getradiostategroups, o, p, r, rilapi/RIL_GetRadioStateGroups, s, t, u"
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
-	RIL_GetRadioStateGroups
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_GetRadioStateGroups function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_GetRadioStateGroups(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwParentGroupId
);
````


## -parameters




### -param hRil


### -param lpContext


### -param dwParentGroupId


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




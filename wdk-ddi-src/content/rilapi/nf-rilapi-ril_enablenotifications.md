---
UID: NF:rilapi.RIL_EnableNotifications
title: RIL_EnableNotifications function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_enablenotifications.htm
old-project: netvista
ms.assetid: 560cb5a3-ac15-4a11-977a-b66caefc2f6b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_EnableNotifications method [Network Drivers Starting with Windows Vista], netvista.ril_enablenotifications, RIL_EnableNotifications, rilapi/RIL_EnableNotifications
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
-	RIL_EnableNotifications
product: Windows
targetos: Windows
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_EnableNotifications function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax


````
HRESULT  RIL_EnableNotifications(
   HRIL   hRil,
   LPVOID usersContext,
   DWORD  lpdwNotifications,
   DWORD  dwNotificationCount
);
````


## -parameters




### -param hRil



### -param usersContext



### -param lpdwNotifications



### -param dwNotificationCount



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



---
UID: NF:knetpwrdepbroker.NpdBrokerAcquireWithTimeout
title: NpdBrokerAcquireWithTimeout function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokeracquirewithtimeout.htm
old-project: netvista
ms.assetid: D2067A72-0FF5-4D77-A1F6-0A6984A1735A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NpdBrokerAcquireWithTimeout, knetpwrdepbroker/NpdBrokerAcquireWithTimeout, NpdBrokerAcquireWithTimeout function [Network Drivers Starting with Windows Vista], netvista.npdbrokeracquirewithtimeout
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: knetpwrdepbroker.h
req.include-header: KNetPwrDepBroker.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	KNetPwrDepBroker.h
apiname:
-	NpdBrokerAcquireWithTimeout
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# NpdBrokerAcquireWithTimeout function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
NTSTATUS NpdBrokerAcquireWithTimeout(
  _In_ HANDLE hBroker,
  _In_ LONG   lTimeoutMS
);
````


## -parameters




#### - hBroker [in]

Reserved.


#### - lTimeoutMS [in]

Reserved.


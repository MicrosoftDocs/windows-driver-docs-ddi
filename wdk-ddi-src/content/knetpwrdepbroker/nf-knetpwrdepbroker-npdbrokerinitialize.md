---
UID: NF:knetpwrdepbroker.NpdBrokerInitialize
title: NpdBrokerInitialize function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\npdbrokerinitialize.htm
old-project: netvista
ms.assetid: 7B23A6DF-2B78-48DF-BDD4-451A19521CAC
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.npdbrokerinitialize, NpdBrokerInitialize, knetpwrdepbroker/NpdBrokerInitialize, NpdBrokerInitialize function [Network Drivers Starting with Windows Vista]
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
-	NpdBrokerInitialize
product: Windows
targetos: Windows
req.typenames: KEYWORDSELECTOR
---

# NpdBrokerInitialize function


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
NTSTATUS NpdBrokerInitialize(
  _In_  ULONG   ulClientID,
  _Out_ PHANDLE phBroker
);
````


## -parameters




### -param ulClientID [in]

Reserved.


### -param phBroker [out]

Reserved.


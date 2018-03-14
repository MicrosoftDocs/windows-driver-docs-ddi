---
UID: NF:prnasntp.IPrintAsyncNotifyServerReferral.GetServerReferral
title: IPrintAsyncNotifyServerReferral::GetServerReferral method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotifyserverreferral_getserverreferral.htm
old-project: print
ms.assetid: 58DD0DA5-CE6A-4C2F-AF7D-B35BCBFB6AFB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetServerReferral method [Print Devices], GetServerReferral method [Print Devices], IPrintAsyncNotifyServerReferral interface, GetServerReferral,IPrintAsyncNotifyServerReferral.GetServerReferral, IPrintAsyncNotifyServerReferral, IPrintAsyncNotifyServerReferral interface [Print Devices], GetServerReferral method, IPrintAsyncNotifyServerReferral::GetServerReferral, print.iprintasyncnotifyserverreferral_getserverreferral, prnasntp/IPrintAsyncNotifyServerReferral::GetServerReferral
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prnasntp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prnasntp.h
api_name:
-	IPrintAsyncNotifyServerReferral.GetServerReferral
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintAsyncNotifyServerReferral::GetServerReferral method


## -description





## -syntax


````
HRESULT GetServerReferral(
  [out] PWSTR *pStr
);
````


## -parameters






#### - pStr [out]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintasyncnotifyserverreferral.md">IPrintAsyncNotifyServerReferral</a>



 

 



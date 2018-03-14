---
UID: NF:prnasntp.IPrintAsyncNotifyServerReferral.SetServerReferral
title: IPrintAsyncNotifyServerReferral::SetServerReferral method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotifyserverreferral_setserverreferral.htm
old-project: print
ms.assetid: 6555386C-8589-424A-9640-530B0C625DE2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintAsyncNotifyServerReferral, IPrintAsyncNotifyServerReferral interface [Print Devices], SetServerReferral method, IPrintAsyncNotifyServerReferral::SetServerReferral, SetServerReferral method [Print Devices], SetServerReferral method [Print Devices], IPrintAsyncNotifyServerReferral interface, SetServerReferral,IPrintAsyncNotifyServerReferral.SetServerReferral, print.iprintasyncnotifyserverreferral_setserverreferral, prnasntp/IPrintAsyncNotifyServerReferral::SetServerReferral
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
-	IPrintAsyncNotifyServerReferral.SetServerReferral
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintAsyncNotifyServerReferral::SetServerReferral method


## -description





## -syntax


````
HRESULT SetServerReferral(
  [in] PCWSTR pRmtServerReferral
);
````


## -parameters




### -param pRmtServerReferral [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintasyncnotifyserverreferral.md">IPrintAsyncNotifyServerReferral</a>



 

 



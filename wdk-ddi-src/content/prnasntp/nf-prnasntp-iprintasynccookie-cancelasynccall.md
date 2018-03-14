---
UID: NF:prnasntp.IPrintAsyncCookie.CancelAsyncCall
title: IPrintAsyncCookie::CancelAsyncCall method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotify_cancelasynccall.htm
old-project: print
ms.assetid: F5228B4C-B5CC-4F7F-91E6-B5BCED76BF7A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CancelAsyncCall method [Print Devices], CancelAsyncCall method [Print Devices], IPrintAsyncCookie interface, CancelAsyncCall,IPrintAsyncCookie.CancelAsyncCall, IPrintAsyncCookie, IPrintAsyncCookie interface [Print Devices], CancelAsyncCall method, IPrintAsyncCookie::CancelAsyncCall, print.iprintasyncnotify_cancelasynccall, prnasntp/IPrintAsyncCookie::CancelAsyncCall
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
-	IPrintAsyncCookie.CancelAsyncCall
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintAsyncCookie::CancelAsyncCall method


## -description





## -syntax


````
HRESULT CancelAsyncCall(
  [in] HRESULT hRes
);
````


## -parameters






#### - hRes [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintasynccookie.md">IPrintAsyncCookie</a>



 

 



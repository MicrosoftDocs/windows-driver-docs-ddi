---
UID: NF:prnasntp.IPrintAsyncCookie.CancelAsyncCall
title: IPrintAsyncCookie::CancelAsyncCall method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotify_cancelasynccall.htm
old-project: print
ms.assetid: F5228B4C-B5CC-4F7F-91E6-B5BCED76BF7A
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: print.iprintasyncnotify_cancelasynccall, CancelAsyncCall, CancelAsyncCall method [Print Devices], IPrintAsyncCookie interface, CancelAsyncCall method [Print Devices], IPrintAsyncCookie::CancelAsyncCall, prnasntp/IPrintAsyncCookie::CancelAsyncCall, IPrintAsyncCookie, IPrintAsyncCookie interface [Print Devices], CancelAsyncCall method
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
req.lib: prnasntp.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prnasntp.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintAsyncCookie::CancelAsyncCall method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


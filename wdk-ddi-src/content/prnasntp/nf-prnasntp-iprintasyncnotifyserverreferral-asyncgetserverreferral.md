---
UID: NF:prnasntp.IPrintAsyncNotifyServerReferral.AsyncGetServerReferral
title: IPrintAsyncNotifyServerReferral::AsyncGetServerReferral method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotifyserverreferral_asyncgetserverreferral.htm
old-project: print
ms.assetid: 6B56E7B6-392E-4664-B96E-249B42A0AF5D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: AsyncGetServerReferral method [Print Devices], IPrintAsyncNotifyServerReferral interface, AsyncGetServerReferral method [Print Devices], AsyncGetServerReferral, prnasntp/IPrintAsyncNotifyServerReferral::AsyncGetServerReferral, IPrintAsyncNotifyServerReferral, IPrintAsyncNotifyServerReferral::AsyncGetServerReferral, print.iprintasyncnotifyserverreferral_asyncgetserverreferral, IPrintAsyncNotifyServerReferral interface [Print Devices], AsyncGetServerReferral method
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
-	IPrintAsyncNotifyServerReferral.AsyncGetServerReferral
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintAsyncNotifyServerReferral::AsyncGetServerReferral method


## -description





## -syntax


````
HRESULT AsyncGetServerReferral(
  [in] IAsyncGetSrvReferralCookie *pCookie
);
````


## -parameters




### -param EQUALNULL






#### - pCookie [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintasyncnotifyserverreferral.md">IPrintAsyncNotifyServerReferral</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintAsyncNotifyServerReferral::AsyncGetServerReferral method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


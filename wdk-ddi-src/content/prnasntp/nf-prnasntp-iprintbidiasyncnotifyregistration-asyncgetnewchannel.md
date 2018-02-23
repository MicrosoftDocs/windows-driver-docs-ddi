---
UID: NF:prnasntp.IPrintBidiAsyncNotifyRegistration.AsyncGetNewChannel
title: IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel method
author: windows-driver-content
description: "."
old-location: print\iprintbidiasyncnotifyregistration_asyncgetnewchannel.htm
old-project: print
ms.assetid: A5E2FA41-0871-4416-B501-051BD67A60AF
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: AsyncGetNewChannel method [Print Devices], IPrintBidiAsyncNotifyRegistration interface [Print Devices], AsyncGetNewChannel method, AsyncGetNewChannel method [Print Devices], IPrintBidiAsyncNotifyRegistration interface, IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel, IPrintBidiAsyncNotifyRegistration, AsyncGetNewChannel, print.iprintbidiasyncnotifyregistration_asyncgetnewchannel, prnasntp/IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel
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
-	IPrintBidiAsyncNotifyRegistration.AsyncGetNewChannel
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel method


## -description





## -syntax


````
HRESULT AsyncGetNewChannel(
  [in] IPrintAsyncNewChannelCookie *pCookie
);
````


## -parameters




### -param EQUALNULL






#### - pCookie [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintbidiasyncnotifyregistration.md">IPrintBidiAsyncNotifyRegistration</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintBidiAsyncNotifyRegistration::AsyncGetNewChannel method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


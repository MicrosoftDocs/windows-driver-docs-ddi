---
UID: NF:prnasntp.IPrintAsyncNotify.CreatePrintAsyncNotifyChannel
title: IPrintAsyncNotify::CreatePrintAsyncNotifyChannel method
author: windows-driver-content
description: "."
old-location: print\iprintasyncnotify_createprintasyncnotifychannel.htm
old-project: print
ms.assetid: B86297A4-1234-46B1-A10B-BD9A6E5012F2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreatePrintAsyncNotifyChannel method [Print Devices], CreatePrintAsyncNotifyChannel method [Print Devices], IPrintAsyncNotify interface, CreatePrintAsyncNotifyChannel,IPrintAsyncNotify.CreatePrintAsyncNotifyChannel, IPrintAsyncNotify, IPrintAsyncNotify interface [Print Devices], CreatePrintAsyncNotifyChannel method, IPrintAsyncNotify::CreatePrintAsyncNotifyChannel, print.iprintasyncnotify_createprintasyncnotifychannel, prnasntp/IPrintAsyncNotify::CreatePrintAsyncNotifyChannel
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prnasntp.h
api_name:
-	IPrintAsyncNotify.CreatePrintAsyncNotifyChannel
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IPrintAsyncNotify::CreatePrintAsyncNotifyChannel method


## -description





## -syntax


````
HRESULT CreatePrintAsyncNotifyChannel(
  [in]  ULONG                             uL,
  [in]  PrintAsyncNotificationType        *pType,
  [in]  PrintAsyncNotifyUserFilter        filter,
  [in]  PrintAsyncNotifyConversationStyle style,
  [in]  IPrintAsyncNotifyCallback         *pCallback,
  [out] IPrintAsyncNotifyChannel          **ppChannel
);
````


## -parameters




### -param






#### - filter [in]


#### - pCallback [in]


#### - pType [in]


#### - ppChannel [out]


#### - style [in]


#### - uL [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-iprintasyncnotify.md">IPrintAsyncNotify</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintAsyncNotify::CreatePrintAsyncNotifyChannel method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


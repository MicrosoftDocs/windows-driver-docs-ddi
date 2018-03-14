---
UID: NF:prnasntp.IBidiAsyncNotifyChannel.CloseChannel
title: IBidiAsyncNotifyChannel::CloseChannel method
author: windows-driver-content
description: "."
old-location: print\ibidiasyncnotifychannel_closechannel.htm
old-project: print
ms.assetid: 30BAA8DD-6FC6-45CD-9EA2-244133865551
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CloseChannel method [Print Devices], CloseChannel method [Print Devices], IBidiAsyncNotifyChannel interface, CloseChannel,IBidiAsyncNotifyChannel.CloseChannel, IBidiAsyncNotifyChannel, IBidiAsyncNotifyChannel interface [Print Devices], CloseChannel method, IBidiAsyncNotifyChannel::CloseChannel, print.ibidiasyncnotifychannel_closechannel, prnasntp/IBidiAsyncNotifyChannel::CloseChannel
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
-	IBidiAsyncNotifyChannel.CloseChannel
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IBidiAsyncNotifyChannel::CloseChannel method


## -description





## -syntax


````
HRESULT CloseChannel(
  [in] IPrintAsyncNotifyDataObject *pObject
);
````


## -parameters






#### - pObject [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-ibidiasyncnotifychannel.md">IBidiAsyncNotifyChannel</a>



 

 



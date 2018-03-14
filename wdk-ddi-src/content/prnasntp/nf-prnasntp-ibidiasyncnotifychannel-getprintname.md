---
UID: NF:prnasntp.IBidiAsyncNotifyChannel.GetPrintName
title: IBidiAsyncNotifyChannel::GetPrintName method
author: windows-driver-content
description: "."
old-location: print\ibidiasyncnotifychannel_getprintname.htm
old-project: print
ms.assetid: DE84073F-8D87-4C72-B820-4CBCF1B9DF2F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetPrintName method [Print Devices], GetPrintName method [Print Devices], IBidiAsyncNotifyChannel interface, GetPrintName,IBidiAsyncNotifyChannel.GetPrintName, IBidiAsyncNotifyChannel, IBidiAsyncNotifyChannel interface [Print Devices], GetPrintName method, IBidiAsyncNotifyChannel::GetPrintName, print.ibidiasyncnotifychannel_getprintname, prnasntp/IBidiAsyncNotifyChannel::GetPrintName
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
-	IBidiAsyncNotifyChannel.GetPrintName
product: Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
req.product: Windows 10 or later.
---

# IBidiAsyncNotifyChannel::GetPrintName method


## -description





## -syntax


````
HRESULT GetPrintName(
  [in] IPrintAsyncNotifyDataObject **ppObject
);
````


## -parameters






#### - ppObject [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prnasntp\nn-prnasntp-ibidiasyncnotifychannel.md">IBidiAsyncNotifyChannel</a>



 

 



---
UID: NF:prcomoem.IPrintOemEngine.EnableDriver
title: IPrintOemEngine::EnableDriver method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_enabledriver.htm
old-project: print
ms.assetid: 638E4FBE-8F53-4509-BFAE-59C02D2D1C4B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintOemEngine::EnableDriver, EnableDriver, EnableDriver method [Print Devices], IPrintOemEngine, print.iprintoemengine_enabledriver, IPrintOemEngine interface [Print Devices], EnableDriver method, EnableDriver method [Print Devices], IPrintOemEngine interface, prcomoem/IPrintOemEngine::EnableDriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prcomoem.h
apiname:
-	IPrintOemEngine.EnableDriver
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemEngine::EnableDriver method


## -description





## -syntax


````
HRESULT EnableDriver(
   DWORD          DriverVersion,
   DWORD          cbSize,
   PDRVENABLEDATA pded
);
````


## -parameters




#### - DriverVersion



#### - cbSize



#### - pded



## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemEngine::EnableDriver method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


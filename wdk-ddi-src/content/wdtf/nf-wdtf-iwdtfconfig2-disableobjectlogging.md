---
UID: NF:wdtf.IWDTFCONFIG2.DisableObjectLogging
title: IWDTFCONFIG2::DisableObjectLogging method
author: windows-driver-content
description: Disables object logging for all objects.
old-location: dtf\iwdtfconfig2_disableobjectlogging.htm
old-project: dtf
ms.assetid: 06a8d1f5-d504-45af-a098-f006e9fa647e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, C, D, DisableObjectLogging method [Windows Device Testing Framework], DisableObjectLogging method [Windows Device Testing Framework], IWDTFCONFIG2 interface, DisableObjectLogging,IWDTFCONFIG2.DisableObjectLogging, F, G, I, IWDTFCONFIG2, IWDTFCONFIG2 interface [Windows Device Testing Framework], DisableObjectLogging method, IWDTFCONFIG2::DisableObjectLogging, L, Microsoft.WDTF.IWDTFCONFIG2.DisableObjectLogging, Microsoft::WDTF::IWDTFCONFIG2::DisableObjectLogging, N, O, T, W, a, b, c, dtf.iwdtfconfig2_disableobjectlogging, e, g, i, j, l, n, o, s, t, wdtf/IWDTFCONFIG2::DisableObjectLogging"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFCONFIG2.DisableObjectLogging
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFCONFIG2::DisableObjectLogging method


## -description


Disables object logging for all objects.


## -syntax


````
HRESULT DisableObjectLogging();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



<b>WDTF</b> logging defaults to disabled. If logging is enabled, 
each <b>WDTF</b> object writes to the 
test scripts log.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfconfig2.md">IWDTFCONFIG2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFCONFIG2::DisableObjectLogging method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


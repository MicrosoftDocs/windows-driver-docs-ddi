---
UID: NF:prcomoem.IPrintOemEngine.EnablePDEV
title: IPrintOemEngine::EnablePDEV method
author: windows-driver-content
description: "."
old-location: print\iprintoemengine_enablepdev.htm
old-project: print
ms.assetid: F84B7A8F-5B75-4E2F-93EB-AFFE24637647
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IPrintOemEngine interface [Print Devices], EnablePDEV method, IPrintOemEngine, print.iprintoemengine_enablepdev, EnablePDEV, prcomoem/IPrintOemEngine::EnablePDEV, EnablePDEV method [Print Devices], IPrintOemEngine::EnablePDEV, EnablePDEV method [Print Devices], IPrintOemEngine interface
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
-	IPrintOemEngine.EnablePDEV
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemEngine::EnablePDEV method


## -description





## -syntax


````
HRESULT EnablePDEV(
   PDEVOBJ       pdevobj,
   PWSTR         pPrinterName,
   ULONG         cPatterns,
   HSURF         *phsurfPatterns,
   ULONG         cjGdiInfo,
   GDIINFO       *pGdiInfo,
   ULONG         cjDevInfo,
   DEVINFO       *pDevInfo,
   DRVENABLEDATA *pded,
   PDEVOEM       *pDevOem
);
````


## -parameters




### -param pdevobj


### -param pPrinterName


### -param cPatterns


### -param phsurfPatterns


### -param cjGdiInfo


### -param pGdiInfo


### -param cjDevInfo


### -param pDevInfo


### -param pded


### -param pDevOem


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\prcomoem\nn-prcomoem-iprintoemengine.md">IPrintOemEngine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemEngine::EnablePDEV method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


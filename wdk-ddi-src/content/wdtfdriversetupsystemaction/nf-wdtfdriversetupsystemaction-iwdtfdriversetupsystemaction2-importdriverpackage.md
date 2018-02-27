---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.ImportDriverPackage
title: IWDTFDriverSetupSystemAction2::ImportDriverPackage method
author: windows-driver-content
description: Imports a driver packge to the system driver store.
old-location: dtf\iwdtfdriversetupsystemaction2_importdriverpackage.htm
old-project: dtf
ms.assetid: dc10fd33-e330-4c74-934b-2d178b17c51b
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], ImportDriverPackage method, IWDTFDriverSetupSystemAction2::ImportDriverPackage, ImportDriverPackage method [Windows Device Testing Framework], ImportDriverPackage method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, ImportDriverPackage,IWDTFDriverSetupSystemAction2.ImportDriverPackage, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.ImportDriverPackage, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::ImportDriverPackage, dtf.iwdtfdriversetupsystemaction2_importdriverpackage, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::ImportDriverPackage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfdriversetupsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupSystemAction.Interop.dll
req.type-library: 
req.lib: wdtfdriversetupsystemaction.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFDriverSetupSystemAction.Interop.dll
api_name:
-	IWDTFDriverSetupSystemAction2.ImportDriverPackage
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverSetupSystemAction2::ImportDriverPackage method


## -description


Imports a driver packge to the system driver store.


## -syntax


````
HRESULT ImportDriverPackage(
  [in] IWDTFDriverPackageAction2 *pDp
);
````


## -parameters




### -param pDp [in]

The driver package to import.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriversetupsystemaction\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md">IWDTFDriverSetupSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupSystemAction2::ImportDriverPackage method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


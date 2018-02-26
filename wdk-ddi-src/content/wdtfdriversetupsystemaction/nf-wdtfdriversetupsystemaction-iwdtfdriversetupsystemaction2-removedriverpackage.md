---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.RemoveDriverPackage
title: IWDTFDriverSetupSystemAction2::RemoveDriverPackage method
author: windows-driver-content
description: Removes a driver package from the driver store.
old-location: dtf\iwdtfdriversetupsystemaction2_removedriverpackage.htm
old-project: dtf
ms.assetid: de742d86-d38c-4d33-b808-678b5cb7419e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, A, D, F, I, IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], RemoveDriverPackage method, IWDTFDriverSetupSystemAction2::RemoveDriverPackage, Microsoft.WDTF.IWDTFDriverSetupSystemAction2.RemoveDriverPackage, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::RemoveDriverPackage, P, R, RemoveDriverPackage method [Windows Device Testing Framework], RemoveDriverPackage method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, RemoveDriverPackage,IWDTFDriverSetupSystemAction2.RemoveDriverPackage, S, T, W, a, c, dtf.iwdtfdriversetupsystemaction2_removedriverpackage, e, g, i, k, m, n, o, p, r, s, t, u, v, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::RemoveDriverPackage, y"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverSetupSystemAction.Interop.dll
apiname:
-	IWDTFDriverSetupSystemAction2.RemoveDriverPackage
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverSetupSystemAction2::RemoveDriverPackage method


## -description


Removes a driver package from the driver store.


## -syntax


````
HRESULT RemoveDriverPackage(
  [in] IWDTFDriverPackageAction2 *pDp
);
````


## -parameters




### -param pDp [in]

The driver package to remove.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriversetupsystemaction\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md">IWDTFDriverSetupSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupSystemAction2::RemoveDriverPackage method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


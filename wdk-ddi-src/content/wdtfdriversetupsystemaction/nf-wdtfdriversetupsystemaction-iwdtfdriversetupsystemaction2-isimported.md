---
UID: NF:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2.IsImported
title: IWDTFDriverSetupSystemAction2::IsImported method
author: windows-driver-content
description: Returns a value that indicates whether a package has already been imported.
old-location: dtf\iwdtfdriversetupsystemaction2_isimported.htm
old-project: dtf
ms.assetid: 2b6e0fc6-33c6-4dcf-8def-b0e081e2405b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: Microsoft.WDTF.IWDTFDriverSetupSystemAction2.IsImported, IsImported method [Windows Device Testing Framework], wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2::IsImported, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], IsImported method, IsImported method [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface, dtf.iwdtfdriversetupsystemaction2_isimported, IWDTFDriverSetupSystemAction2::IsImported, IsImported, IWDTFDriverSetupSystemAction2, Microsoft::WDTF::IWDTFDriverSetupSystemAction2::IsImported
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
-	IWDTFDriverSetupSystemAction2.IsImported
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFDriverSetupSystemAction2::IsImported method


## -description


Returns a value that indicates whether a package has already been imported.


## -syntax


````
HRESULT IsImported(
  [in]          IWDTFDriverPackageAction2 *pDp,
  [out, retval] VARIANT_BOOL              *pbIsImported
);
````


## -parameters




### -param pDp [in]

The package that is to be checked.


### -param bRet






#### - pbIsImported [out, retval]

True if the package has already been imported; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfdriversetupsystemaction\nn-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2.md">IWDTFDriverSetupSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDriverSetupSystemAction2::IsImported method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


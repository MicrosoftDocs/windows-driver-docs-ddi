---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Start
title: IWDTFSimpleIOStressAction2::Start method
author: windows-driver-content
description: Opens the device.
old-location: dtf\iwdtfsimpleiostressaction2_start.htm
old-project: dtf
ms.assetid: 4f25224b-5d8c-4d9d-8350-d84b3b75d780
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., 2, :, A, D, F, I, IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Start method, IWDTFSimpleIOStressAction2::Start, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Start, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Start, O, S, Start method [Windows Device Testing Framework], Start method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, Start,IWDTFSimpleIOStressAction2.Start, T, W, a, c, dtf.iwdtfsimpleiostressaction2_start, e, i, l, m, n, o, p, r, s, t, wdtfinterfaces/IWDTFSimpleIOStressAction2::Start"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfinterfaces.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFInterfaces.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFInterfaces.Interop.dll
req.type-library: 
req.lib: wdtfinterfaces.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFInterfaces.Interop.dll
apiname:
-	IWDTFSimpleIOStressAction2.Start
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimpleIOStressAction2::Start method


## -description


Opens the device.


## -syntax


````
HRESULT Start(
  [out, retval] VARIANT_BOOL *pResult
);
````


## -parameters




### -param pResult [out, retval]

True if the device opens; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md">IWDTFSimpleIOStressAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOStressAction2::Start method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


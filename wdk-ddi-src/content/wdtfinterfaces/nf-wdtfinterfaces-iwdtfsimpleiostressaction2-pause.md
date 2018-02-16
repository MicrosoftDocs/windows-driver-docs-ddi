---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Pause
title: IWDTFSimpleIOStressAction2::Pause method
author: windows-driver-content
description: Pauses the I/O.
old-location: dtf\iwdtfsimpleiostressaction2_pause.htm
old-project: dtf
ms.assetid: 9a0c66cd-3065-4532-8543-22d6f202fb74
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFSimpleIOStressAction2::Pause, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Pause, dtf.iwdtfsimpleiostressaction2_pause, wdtfinterfaces/IWDTFSimpleIOStressAction2::Pause, Pause method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, IWDTFSimpleIOStressAction2, Pause method [Windows Device Testing Framework], Pause, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Pause, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Pause method
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
-	IWDTFSimpleIOStressAction2.Pause
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFSimpleIOStressAction2::Pause method


## -description


Pauses the I/O.


## -syntax


````
HRESULT Pause(
  [out, retval] VARIANT_BOOL *pResult
);
````


## -parameters




### -param pResult [out, retval]

True if the I/O operation after the last 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> or 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451185">Continue</a> succeeded; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleiostressaction2.md">IWDTFSimpleIOStressAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOStressAction2::Pause method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


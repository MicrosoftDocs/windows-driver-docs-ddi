---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.Sleep
title: IWDTFSystemAction2::Sleep method
author: windows-driver-content
description: Puts the system into the desired sleep state.
old-location: dtf\iwdtfsystemaction2_sleep.htm
old-project: dtf
ms.assetid: 4DC3E14E-6FC3-49C1-AB22-779D0E8CA68D
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], Sleep method, IWDTFSystemAction2::Sleep, Microsoft.WDTF.IWDTFSystemAction2.Sleep, Microsoft::WDTF::IWDTFSystemAction2::Sleep, Sleep method [Windows Device Testing Framework], Sleep method [Windows Device Testing Framework], IWDTFSystemAction2 interface, Sleep,IWDTFSystemAction2.Sleep, dtf.iwdtfsystemaction2_sleep, wdtfsystemaction/IWDTFSystemAction2::Sleep
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
req.type-library: 
req.lib: wdtfsystemaction.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.Sleep
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::Sleep method


## -description


Puts the system into the desired sleep state.


## -syntax


````
HRESULT Sleep(
  [in] LONG nSleepState
);
````


## -parameters




### -param nSleepState [in]

The sleep state.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::Sleep method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


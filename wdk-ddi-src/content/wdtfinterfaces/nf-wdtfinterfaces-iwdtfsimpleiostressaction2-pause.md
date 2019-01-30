---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Pause
title: IWDTFSimpleIOStressAction2::Pause (wdtfinterfaces.h)
description: Pauses the I/O.
old-location: dtf\iwdtfsimpleiostressaction2_pause.htm
tech.root: dtf
ms.assetid: 9a0c66cd-3065-4532-8543-22d6f202fb74
ms.date: 04/04/2018
ms.keywords: IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework],Pause method, IWDTFSimpleIOStressAction2.Pause, IWDTFSimpleIOStressAction2::Pause, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Pause, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Pause, Pause, Pause method [Windows Device Testing Framework], Pause method [Windows Device Testing Framework],IWDTFSimpleIOStressAction2 interface, dtf.iwdtfsimpleiostressaction2_pause, wdtfinterfaces/IWDTFSimpleIOStressAction2::Pause
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFInterfaces.Interop.dll
api_name:
-	IWDTFSimpleIOStressAction2.Pause
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOStressAction2::Pause


## -description


Pauses the I/O.


## -parameters




### -param pResult [out, retval]

True if the I/O operation after the last 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> or 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451185">Continue</a> succeeded; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451157">IWDTFSimpleIOStressAction2</a>
 

 


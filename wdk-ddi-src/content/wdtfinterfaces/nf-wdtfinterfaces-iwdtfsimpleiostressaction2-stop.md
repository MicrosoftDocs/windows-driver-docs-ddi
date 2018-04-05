---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Stop
title: IWDTFSimpleIOStressAction2::Stop method
author: windows-driver-content
description: Stops the device.
old-location: dtf\iwdtfsimpleiostressaction2_stop.htm
old-project: dtf
ms.assetid: d813b9f4-95f7-49cd-97c0-08a04dbd362e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSimpleIOStressAction2, IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework], Stop method, IWDTFSimpleIOStressAction2::Stop, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Stop, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Stop, Stop method [Windows Device Testing Framework], Stop method [Windows Device Testing Framework], IWDTFSimpleIOStressAction2 interface, Stop,IWDTFSimpleIOStressAction2.Stop, dtf.iwdtfsimpleiostressaction2_stop, wdtfinterfaces/IWDTFSimpleIOStressAction2::Stop
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
-	IWDTFSimpleIOStressAction2.Stop
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimpleIOStressAction2::Stop method


## -description


Stops the device.


## -parameters




### -param pResult [out, retval]

True if all of the I/O operations after the last 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> or 
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451185">Continue</a> succeeded; 
otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451157">IWDTFSimpleIOStressAction2</a>
 

 


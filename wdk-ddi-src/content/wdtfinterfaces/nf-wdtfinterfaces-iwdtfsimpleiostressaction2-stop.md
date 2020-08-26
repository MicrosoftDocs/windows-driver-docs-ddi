---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Stop
title: IWDTFSimpleIOStressAction2::Stop (wdtfinterfaces.h)
description: Stops the device.
old-location: dtf\iwdtfsimpleiostressaction2_stop.htm
tech.root: dtf
ms.assetid: d813b9f4-95f7-49cd-97c0-08a04dbd362e
ms.date: 04/04/2018
keywords: ["IWDTFSimpleIOStressAction2::Stop"]
ms.keywords: IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework],Stop method, IWDTFSimpleIOStressAction2.Stop, IWDTFSimpleIOStressAction2::Stop, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Stop, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Stop, Stop, Stop method [Windows Device Testing Framework], Stop method [Windows Device Testing Framework],IWDTFSimpleIOStressAction2 interface, dtf.iwdtfsimpleiostressaction2_stop, wdtfinterfaces/IWDTFSimpleIOStressAction2::Stop
f1_keywords:
 - "wdtfinterfaces/IWDTFSimpleIOStressAction2.Stop"
 - "IWDTFSimpleIOStressAction2.Stop"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFInterfaces.Interop.dll
api_name:
- IWDTFSimpleIOStressAction2.Stop
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOStressAction2::Stop


## -description


Stops the device.


## -parameters




### -param pResult 
[out, retval]
True if all of the I/O operations after the last 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start">Start</a> or 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Continue</a> succeeded; 
otherwise, false.


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleiostressaction2">IWDTFSimpleIOStressAction2</a>
 

 


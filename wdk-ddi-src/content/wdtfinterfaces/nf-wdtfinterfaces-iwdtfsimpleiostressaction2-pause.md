---
UID: NF:wdtfinterfaces.IWDTFSimpleIOStressAction2.Pause
title: IWDTFSimpleIOStressAction2::Pause (wdtfinterfaces.h)
description: Pauses the I/O.
old-location: dtf\iwdtfsimpleiostressaction2_pause.htm
tech.root: dtf
ms.assetid: 9a0c66cd-3065-4532-8543-22d6f202fb74
ms.date: 04/04/2018
keywords: ["IWDTFSimpleIOStressAction2::Pause"]
ms.keywords: IWDTFSimpleIOStressAction2 interface [Windows Device Testing Framework],Pause method, IWDTFSimpleIOStressAction2.Pause, IWDTFSimpleIOStressAction2::Pause, Microsoft.WDTF.IWDTFSimpleIOStressAction2.Pause, Microsoft::WDTF::IWDTFSimpleIOStressAction2::Pause, Pause, Pause method [Windows Device Testing Framework], Pause method [Windows Device Testing Framework],IWDTFSimpleIOStressAction2 interface, dtf.iwdtfsimpleiostressaction2_pause, wdtfinterfaces/IWDTFSimpleIOStressAction2::Pause
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSimpleIOStressAction2::Pause
 - wdtfinterfaces/IWDTFSimpleIOStressAction2::Pause
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFInterfaces.Interop.dll
api_name:
 - IWDTFSimpleIOStressAction2.Pause
---

# IWDTFSimpleIOStressAction2::Pause


## -description

Pauses the I/O.

## -parameters

### -param pResult 

[out, retval]
True if the I/O operation after the last 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printerextension/nf-printerextension-iprintschemaasyncoperation-start">Start</a> or 
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Continue</a> succeeded; 
otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleiostressaction2">IWDTFSimpleIOStressAction2</a>


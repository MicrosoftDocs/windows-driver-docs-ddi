---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingStart
title: IWDTFSystemAction2::PowerTracingStart (wdtfsystemaction.h)
description: Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method is available starting with Windows 8.
old-location: dtf\iwdtfsystemaction2_powertracingstart.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::PowerTracingStart"]
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],PowerTracingStart method, IWDTFSystemAction2.PowerTracingStart, IWDTFSystemAction2::PowerTracingStart, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingStart, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingStart, PowerTracingStart, PowerTracingStart method [Windows Device Testing Framework], PowerTracingStart method [Windows Device Testing Framework],IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_powertracingstart, wdtfsystemaction/IWDTFSystemAction2::PowerTracingStart
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSystemAction2::PowerTracingStart
 - wdtfsystemaction/IWDTFSystemAction2::PowerTracingStart
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFSystemAction.Interop.dll
api_name:
 - IWDTFSystemAction2::PowerTracingStart
---

# IWDTFSystemAction2::PowerTracingStart


## -description

Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method
    is available starting with Windows 8.


Starts a trace for power state transitions and saves an .etl file in the current working directory

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>


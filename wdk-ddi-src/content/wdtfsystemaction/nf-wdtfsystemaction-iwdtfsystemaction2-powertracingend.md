---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingEnd
title: IWDTFSystemAction2::PowerTracingEnd (wdtfsystemaction.h)
description: This method ends a power trace session.
old-location: dtf\iwdtfsystemaction2_powertracingend.htm
tech.root: dtf
ms.assetid: d27678cb-8aad-4cbe-a65e-64828ff4944a
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::PowerTracingEnd"]
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],PowerTracingEnd method, IWDTFSystemAction2.PowerTracingEnd, IWDTFSystemAction2::PowerTracingEnd, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingEnd, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingEnd, PowerTracingEnd, PowerTracingEnd method [Windows Device Testing Framework], PowerTracingEnd method [Windows Device Testing Framework],IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_powertracingend, wdtfsystemaction/IWDTFSystemAction2::PowerTracingEnd
f1_keywords:
 - "wdtfsystemaction/IWDTFSystemAction2.PowerTracingEnd"
 - "IWDTFSystemAction2.PowerTracingEnd"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFSystemAction.Interop.dll
api_name:
- IWDTFSystemAction2.PowerTracingEnd
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemAction2::PowerTracingEnd


## -description


This method ends a power trace session. Any power state events that occurred between the last <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstart">PowerTracingStart</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfsystemaction/nf-wdtfsystemaction-iwdtfsystemaction2-powertracingstartbyfile">PowerTracingStartByFile</a>  method and this
    end method will be captured in the associated trace message (.etl) log file. In addition, the related namespace and fields for the system and any applicable devices
    can be queried.



## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>
 

 


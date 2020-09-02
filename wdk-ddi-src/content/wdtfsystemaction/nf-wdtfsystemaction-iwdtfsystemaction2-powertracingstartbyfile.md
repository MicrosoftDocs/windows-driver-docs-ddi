---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingStartByFile
title: IWDTFSystemAction2::PowerTracingStartByFile (wdtfsystemaction.h)
description: Starts a trace session for power state transitions and saves the trace message file (.etl) using the specified path. This method is available starting with Windows 8.
old-location: dtf\iwdtfsystemaction2_powertracingstartbyfile.htm
tech.root: dtf
ms.assetid: c37095d2-fbf5-49fa-a6c8-b4776bf530af
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::PowerTracingStartByFile"]
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],PowerTracingStartByFile method, IWDTFSystemAction2.PowerTracingStartByFile, IWDTFSystemAction2::PowerTracingStartByFile, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingStartByFile, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingStartByFile, PowerTracingStartByFile, PowerTracingStartByFile method [Windows Device Testing Framework], PowerTracingStartByFile method [Windows Device Testing Framework],IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_powertracingstartbyfile, wdtfsystemaction/IWDTFSystemAction2::PowerTracingStartByFile
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
 - IWDTFSystemAction2::PowerTracingStartByFile
 - wdtfsystemaction/IWDTFSystemAction2::PowerTracingStartByFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFSystemAction.Interop.dll
api_name:
 - IWDTFSystemAction2.PowerTracingStartByFile
---

# IWDTFSystemAction2::PowerTracingStartByFile


## -description

Starts a trace session for power state transitions and saves the trace message file (.etl) using the specified path. This method is available starting with Windows 8.

## -parameters

### -param EventFilePath 

[in]
Specifies the location to store the trace message (.etl)
    log file.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>


---
UID: NF:wdtfinterfaces.IWDTFSimpleIOEx2.Open
title: IWDTFSimpleIOEx2::Open (wdtfinterfaces.h)
description: Opens the device.
old-location: dtf\iwdtfsimpleioex2_open.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSimpleIOEx2::Open"]
ms.keywords: IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],Open method, IWDTFSimpleIOEx2.Open, IWDTFSimpleIOEx2::Open, Microsoft.WDTF.IWDTFSimpleIOEx2.Open, Microsoft::WDTF::IWDTFSimpleIOEx2::Open, Open, Open method [Windows Device Testing Framework], Open method [Windows Device Testing Framework],IWDTFSimpleIOEx2 interface, dtf.iwdtfsimpleioex2_open, wdtfinterfaces/IWDTFSimpleIOEx2::Open
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
 - IWDTFSimpleIOEx2::Open
 - wdtfinterfaces/IWDTFSimpleIOEx2::Open
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFInterfaces.Interop.dll
api_name:
 - IWDTFSimpleIOEx2::Open
---

# IWDTFSimpleIOEx2::Open


## -description

Opens the device.

## -parameters

### -param pResult [out, retval]


True if the operation succeeds; otherwise, false.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

You should call the <b>Open</b> method before calling 
the <a href="/windows-hardware/drivers/ddi/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleioex2-performio">IWDTFSimpleIOEx2::PerformIO</a> method.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleioex2">IWDTFSimpleIOEx2</a>


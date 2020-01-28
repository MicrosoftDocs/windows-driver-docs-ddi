---
UID: NF:wdtfinterfaces.IWDTFSimpleIOEx2.PerformIO
title: IWDTFSimpleIOEx2::PerformIO (wdtfinterfaces.h)
description: Performs a small amount of simple I/O to the device.
old-location: dtf\iwdtfsimpleioex2_performio.htm
tech.root: dtf
ms.assetid: 795dcbed-e0ce-444d-a6a8-95d0bc658f5b
ms.date: 04/04/2018
ms.keywords: IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],PerformIO method, IWDTFSimpleIOEx2.PerformIO, IWDTFSimpleIOEx2::PerformIO, Microsoft.WDTF.IWDTFSimpleIOEx2.PerformIO, Microsoft::WDTF::IWDTFSimpleIOEx2::PerformIO, PerformIO, PerformIO method [Windows Device Testing Framework], PerformIO method [Windows Device Testing Framework],IWDTFSimpleIOEx2 interface, dtf.iwdtfsimpleioex2_performio, wdtfinterfaces/IWDTFSimpleIOEx2::PerformIO
f1_keywords:
 - "wdtfinterfaces/IWDTFSimpleIOEx2.PerformIO"
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
- IWDTFSimpleIOEx2.PerformIO
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOEx2::PerformIO


## -description


Performs a small amount of simple I/O to the device.


## -parameters




### -param pResult [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



<h3>C++</h3>
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

<h3>C# and VB.NET</h3>
True if the operation succeeds; otherwise, false.




## -remarks



You should call the <b>PerformIO</b> method only after calling 
the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfinterfaces/nf-wdtfinterfaces-iwdtfsimpleioex2-open">IWDTFSimpleIOEx2::Open</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfinterfaces/nn-wdtfinterfaces-iwdtfsimpleioex2">IWDTFSimpleIOEx2</a>
 

 


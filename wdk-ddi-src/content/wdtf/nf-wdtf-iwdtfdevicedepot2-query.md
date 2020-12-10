---
UID: NF:wdtf.IWDTFDeviceDepot2.Query
title: IWDTFDeviceDepot2::Query (wdtf.h)
description: Returns a subset of the devices in the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_query.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFDeviceDepot2::Query"]
ms.keywords: IWDTFDeviceDepot2 interface [Windows Device Testing Framework],Query method, IWDTFDeviceDepot2.Query, IWDTFDeviceDepot2::Query, Microsoft.WDTF.IWDTFDeviceDepot2.Query, Microsoft::WDTF::IWDTFDeviceDepot2::Query, Query, Query method [Windows Device Testing Framework], Query method [Windows Device Testing Framework],IWDTFDeviceDepot2 interface, dtf.iwdtfdevicedepot2_query, wdtf/IWDTFDeviceDepot2::Query
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFDeviceDepot2::Query
 - wdtf/IWDTFDeviceDepot2::Query
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTF.Interop.metadata_dll.dll
api_name:
 - IWDTFDeviceDepot2.Query
---

# IWDTFDeviceDepot2::Query


## -description

Returns a subset of the devices in the DeviceDepot.

## -parameters

### -param SDEL 

[in]
The SDEL query string.

### -param ppTargets 

[out, retval]
The collection of devices.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

The <b>Query</b> method provides the <i>SDEL</i> 
parameter in a call to the <a href="/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-eval">IWDTFTarget2::Eval</a> 
method for every instance of the <a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a> interface 
in the <a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a> collection. 
Use the <a href="/windows-hardware/drivers/wdtf/simple-data-evaluation-language-overview">Simple Data 
Evaluation Language</a> to specify this parameter. 
Every target that returns <b>VARIANT_TRUE</b> is added to a new 
instance of the <b>IWDTFTargets2</b> collection 
interface.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfdevicedepot2">IWDTFDeviceDepot2</a>

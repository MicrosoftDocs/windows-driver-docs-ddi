---
UID: NF:wdtf.IWDTFDeviceDepot2.QuerySingle
title: IWDTFDeviceDepot2::QuerySingle (wdtf.h)
description: Returns a single target device from the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_querysingle.htm
tech.root: dtf
ms.assetid: 5e471ede-3607-4d4d-a3f0-5396cc62c6c5
ms.date: 04/04/2018
ms.keywords: IWDTFDeviceDepot2 interface [Windows Device Testing Framework],QuerySingle method, IWDTFDeviceDepot2.QuerySingle, IWDTFDeviceDepot2::QuerySingle, Microsoft.WDTF.IWDTFDeviceDepot2.QuerySingle, Microsoft::WDTF::IWDTFDeviceDepot2::QuerySingle, QuerySingle, QuerySingle method [Windows Device Testing Framework], QuerySingle method [Windows Device Testing Framework],IWDTFDeviceDepot2 interface, dtf.iwdtfdevicedepot2_querysingle, wdtf/IWDTFDeviceDepot2::QuerySingle
ms.topic: method
f1_keywords:
 - "wdtf/IWDTFDeviceDepot2.QuerySingle"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IWDTFDeviceDepot2.QuerySingle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDeviceDepot2::QuerySingle


## -description


Returns a single target device from the DeviceDepot.


## -parameters




### -param SDEL [in]

The SDEL query string.


### -param ppTarget [out, retval]

The requested device.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtfdevicedepot2">IWDTFDeviceDepot2</a>
 

 


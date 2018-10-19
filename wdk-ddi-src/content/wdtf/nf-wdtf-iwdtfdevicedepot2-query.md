---
UID: NF:wdtf.IWDTFDeviceDepot2.Query
title: IWDTFDeviceDepot2::Query
author: windows-driver-content
description: Returns a subset of the devices in the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_query.htm
tech.root: dtf
ms.assetid: f8b0cb77-828a-43c7-b0f3-34eca0da49bf
ms.date: 04/04/2018
ms.keywords: IWDTFDeviceDepot2 interface [Windows Device Testing Framework],Query method, IWDTFDeviceDepot2.Query, IWDTFDeviceDepot2::Query, Microsoft.WDTF.IWDTFDeviceDepot2.Query, Microsoft::WDTF::IWDTFDeviceDepot2::Query, Query, Query method [Windows Device Testing Framework], Query method [Windows Device Testing Framework],IWDTFDeviceDepot2 interface, dtf.iwdtfdevicedepot2_query, wdtf/IWDTFDeviceDepot2::Query
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFDeviceDepot2.Query
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDeviceDepot2::Query


## -description


Returns a subset of the devices in the DeviceDepot.


## -parameters




### -param SDEL [in]

The SDEL query string.


### -param ppTargets [out, retval]

The collection of devices.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The <b>Query</b> method provides the <i>SDEL</i> 
parameter in a call to the <a href="https://msdn.microsoft.com/468cb35d-f816-4233-ba07-8dc47b77d442">IWDTFTarget2::Eval</a> 
method for every instance of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface 
in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a> collection. 
Use the <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">Simple Data 
Evaluation Language</a> to specify this parameter. 
Every target that returns <b>VARIANT_TRUE</b> is added to a new 
instance of the <b>IWDTFTargets2</b> collection 
interface.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh406391">IWDTFDeviceDepot2</a>
 

 


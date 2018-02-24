---
UID: NF:wdtf.IWDTFDeviceDepot2.Query
title: IWDTFDeviceDepot2::Query method
author: windows-driver-content
description: Returns a subset of the devices in the DeviceDepot.
old-location: dtf\iwdtfdevicedepot2_query.htm
old-project: dtf
ms.assetid: f8b0cb77-828a-43c7-b0f3-34eca0da49bf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDTFDeviceDepot2 interface [Windows Device Testing Framework], Query method, Microsoft.WDTF.IWDTFDeviceDepot2.Query, IWDTFDeviceDepot2::Query, Query, wdtf/IWDTFDeviceDepot2::Query, IWDTFDeviceDepot2, Query method [Windows Device Testing Framework], IWDTFDeviceDepot2 interface, Microsoft::WDTF::IWDTFDeviceDepot2::Query, dtf.iwdtfdevicedepot2_query, Query method [Windows Device Testing Framework]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IWDTFDeviceDepot2.Query
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDeviceDepot2::Query method


## -description


Returns a subset of the devices in the DeviceDepot.


## -syntax


````
HRESULT Query(
  [in]          BSTR          SDEL,
  [out, retval] IWDTFTargets2 **ppTargets
);
````


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
method for every instance of the <a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> interface 
in the <a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a> collection. 
Use the <a href="https://msdn.microsoft.com/84c2a1d6-6bec-4aeb-b858-c29f50d74390">Simple Data 
Evaluation Language</a> to specify this parameter. 
Every target that returns <b>VARIANT_TRUE</b> is added to a new 
instance of the <b>IWDTFTargets2</b> collection 
interface.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfdevicedepot2.md">IWDTFDeviceDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFDeviceDepot2::Query method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


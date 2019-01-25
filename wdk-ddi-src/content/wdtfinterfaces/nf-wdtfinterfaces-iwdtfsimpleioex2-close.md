---
UID: NF:wdtfinterfaces.IWDTFSimpleIOEx2.Close
title: IWDTFSimpleIOEx2::Close (wdtfinterfaces.h)
description: Closes the device.
old-location: dtf\iwdtfsimpleioex2_close.htm
tech.root: dtf
ms.assetid: e8061408-2efe-4620-bc57-4cf0c3e41874
ms.date: 04/04/2018
ms.keywords: Close, Close method [Windows Device Testing Framework], Close method [Windows Device Testing Framework],IWDTFSimpleIOEx2 interface, IWDTFSimpleIOEx2 interface [Windows Device Testing Framework],Close method, IWDTFSimpleIOEx2.Close, IWDTFSimpleIOEx2::Close, Microsoft.WDTF.IWDTFSimpleIOEx2.Close, Microsoft::WDTF::IWDTFSimpleIOEx2::Close, dtf.iwdtfsimpleioex2_close, wdtfinterfaces/IWDTFSimpleIOEx2::Close
ms.topic: method
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFInterfaces.Interop.dll
api_name:
-	IWDTFSimpleIOEx2.Close
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimpleIOEx2::Close


## -description


Closes the device.


## -parameters




### -param pResult [out, retval]

True if the operation succeeds; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



You should call the <b>Close</b> method only after calling 
the <a href="https://msdn.microsoft.com/991a60a0-8d82-4f41-8cfe-bf633338bdda">IWDTFSimpleIOEx2::Open</a> method.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451149">IWDTFSimpleIOEx2</a>
 

 


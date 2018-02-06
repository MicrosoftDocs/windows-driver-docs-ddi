---
UID: NF:wdtfinterfaces.IWDTFSimpleIOEx2.Open
title: IWDTFSimpleIOEx2::Open method
author: windows-driver-content
description: Opens the device.
old-location: dtf\iwdtfsimpleioex2_open.htm
old-project: dtf
ms.assetid: 991a60a0-8d82-4f41-8cfe-bf633338bdda
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFSimpleIOEx2 interface [Windows Device Testing Framework], Open method, IWDTFSimpleIOEx2::Open, Open, wdtfinterfaces/IWDTFSimpleIOEx2::Open, Open method [Windows Device Testing Framework], IWDTFSimpleIOEx2 interface, dtf.iwdtfsimpleioex2_open, Microsoft.WDTF.IWDTFSimpleIOEx2.Open, Microsoft::WDTF::IWDTFSimpleIOEx2::Open, IWDTFSimpleIOEx2, Open method [Windows Device Testing Framework]
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: wdtfinterfaces.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFInterfaces.Interop.dll
apiname:
-	IWDTFSimpleIOEx2.Open
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFSimpleIOEx2::Open method


## -description


Opens the device.


## -syntax


````
HRESULT Open(
  [out, retval] VARIANT_BOOL *pResult
);
````


## -parameters




### -param pResult [out, retval]

True if the operation succeeds; otherwise, false.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -remarks


You should call the <b>Open</b> method before calling 
the <a href="https://msdn.microsoft.com/795dcbed-e0ce-444d-a6a8-95d0bc658f5b">IWDTFSimpleIOEx2::PerformIO</a> method.



## -see-also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleioex2.md">IWDTFSimpleIOEx2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOEx2::Open method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wdtfinterfaces.IWDTFSimpleIOEx2.PerformIO
title: IWDTFSimpleIOEx2::PerformIO method
author: windows-driver-content
description: Performs a small amount of simple I/O to the device.
old-location: dtf\iwdtfsimpleioex2_performio.htm
old-project: dtf
ms.assetid: 795dcbed-e0ce-444d-a6a8-95d0bc658f5b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFSimpleIOEx2::PerformIO, Microsoft::WDTF::IWDTFSimpleIOEx2::PerformIO, PerformIO method [Windows Device Testing Framework], IWDTFSimpleIOEx2 interface, Microsoft.WDTF.IWDTFSimpleIOEx2.PerformIO, PerformIO method [Windows Device Testing Framework], PerformIO, IWDTFSimpleIOEx2, wdtfinterfaces/IWDTFSimpleIOEx2::PerformIO, IWDTFSimpleIOEx2 interface [Windows Device Testing Framework], PerformIO method, dtf.iwdtfsimpleioex2_performio
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
-	IWDTFSimpleIOEx2.PerformIO
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFSimpleIOEx2::PerformIO method


## -description


Performs a small amount of simple I/O to the device.


## -syntax


````
HRESULT PerformIO(
  [out, retval] VARIANT_BOOL *pResult
);
````


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
the <a href="https://msdn.microsoft.com/991a60a0-8d82-4f41-8cfe-bf633338bdda">IWDTFSimpleIOEx2::Open</a> method.




## -see-also

<a href="..\wdtfinterfaces\nn-wdtfinterfaces-iwdtfsimpleioex2.md">IWDTFSimpleIOEx2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimpleIOEx2::PerformIO method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


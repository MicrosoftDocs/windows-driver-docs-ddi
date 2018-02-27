---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingEnd
title: IWDTFSystemAction2::PowerTracingEnd method
author: windows-driver-content
description: This method ends a power trace session.
old-location: dtf\iwdtfsystemaction2_powertracingend.htm
old-project: dtf
ms.assetid: d27678cb-8aad-4cbe-a65e-64828ff4944a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], PowerTracingEnd method, IWDTFSystemAction2::PowerTracingEnd, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingEnd, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingEnd, PowerTracingEnd method [Windows Device Testing Framework], PowerTracingEnd method [Windows Device Testing Framework], IWDTFSystemAction2 interface, PowerTracingEnd,IWDTFSystemAction2.PowerTracingEnd, dtf.iwdtfsystemaction2_powertracingend, wdtfsystemaction/IWDTFSystemAction2::PowerTracingEnd
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wdtfsystemaction.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.PowerTracingEnd
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::PowerTracingEnd method


## -description


This method ends a power trace session. Any power state events that occurred between the last <a href="https://msdn.microsoft.com/b82ebd99-289e-4761-9717-ce09cf5c40f0">PowerTracingStart</a> or <a href="https://msdn.microsoft.com/c37095d2-fbf5-49fa-a6c8-b4776bf530af">PowerTracingStartByFile</a>  method and this
    end method will be captured in the associated trace message (.etl) log file. In addition, the related namespace and fields for the system and any applicable devices
    can be queried.



## -syntax


````
HRESULT PowerTracingEnd();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::PowerTracingEnd method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:wdtf.IWDTFSystemDepot2.get_ThisSystem
title: IWDTFSystemDepot2::get_ThisSystem method
author: windows-driver-content
description: Gets an IWDTFTarget2 value that represents the local computer.
old-location: dtf\iwdtfsystemdepot2_thissystem.htm
old-project: dtf
ms.assetid: 8bf680a9-3779-447c-99b0-813ec454658e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemDepot2, IWDTFSystemDepot2 interface [Windows Device Testing Framework], ThisSystem property, IWDTFSystemDepot2.ThisSystem, IWDTFSystemDepot2::get_ThisSystem, Microsoft.WDTF.IWDTFSystemDepot2.ThisSystem, Microsoft::WDTF::IWDTFSystemDepot2::ThisSystem, ThisSystem property [Windows Device Testing Framework], ThisSystem property [Windows Device Testing Framework], IWDTFSystemDepot2 interface, dtf.iwdtfsystemdepot2_thissystem, get_ThisSystem,IWDTFSystemDepot2.get_ThisSystem, wdtf/IWDTFSystemDepot2::ThisSystem, wdtf/IWDTFSystemDepot2::get_ThisSystem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFSystemDepot2.ThisSystem
-	IWDTFSystemDepot2.get_ThisSystem
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemDepot2::get_ThisSystem method


## -description


Gets an <a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a> value that represents the local computer.

This property is read-only.


## -syntax


````
HRESULT get_ThisSystem(
  [out, retval] IWDTFTarget2 **pVal
);
````


## -parameters


## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



<a href="..\wdtf\nn-wdtf-iwdtfsystemdepot2.md">IWDTFSystemDepot2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemDepot2::ThisSystem property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


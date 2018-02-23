---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.get_Critical
title: IWDTFSystemAction2::get_Critical method
author: windows-driver-content
description: Gets or sets a value that indicates whether the the system power state is critical.
old-location: dtf\iwdtfsystemaction2_critical.htm
old-project: dtf
ms.assetid: 173cf6f2-7c6c-41d5-bd30-e323b24a0db0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDTFSystemAction2::put_Critical, wdtfsystemaction/IWDTFSystemAction2::put_Critical, get_Critical, Critical property [Windows Device Testing Framework], IWDTFSystemAction2 interface, wdtfsystemaction/IWDTFSystemAction2::Critical, Microsoft.WDTF.IWDTFSystemAction2.Critical, IWDTFSystemAction2.Critical, IWDTFSystemAction2::get_Critical, IWDTFSystemAction2, dtf.iwdtfsystemaction2_critical, Critical property [Windows Device Testing Framework], IWDTFSystemAction2 interface [Windows Device Testing Framework], Critical property, Microsoft::WDTF::IWDTFSystemAction2::Critical, wdtfsystemaction/IWDTFSystemAction2::get_Critical
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFSystemAction.Interop.dll
apiname:
-	IWDTFSystemAction2.Critical
-	IWDTFSystemAction2.get_Critical
-	IWDTFSystemAction2.put_Critical
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::get_Critical method


## -description


Gets or sets a value that indicates whether the the system power state is critical.

This property is read/write.


## -syntax


````
HRESULT put_Critical(
  [in]          VARIANT_BOOL bCritical
);

HRESULT get_Critical(
  [out, retval] VARIANT_BOOL *pbCritical
);
````


## -parameters


## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::Critical property%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


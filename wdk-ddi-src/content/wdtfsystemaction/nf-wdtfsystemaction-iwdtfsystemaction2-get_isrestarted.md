---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.get_IsRestarted
title: IWDTFSystemAction2::get_IsRestarted method
author: windows-driver-content
description: Gets a value that indicates whether the test script restarted as a result of a call to RebootRestart or RebootRestartWithContext.
old-location: dtf\iwdtfsystemaction2_isrestarted.htm
old-project: dtf
ms.assetid: EF89D020-BA9F-4698-B82A-7671DBE3FDE8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], IsRestarted property, IWDTFSystemAction2.IsRestarted, IWDTFSystemAction2::get_IsRestarted, IsRestarted property [Windows Device Testing Framework], IsRestarted property [Windows Device Testing Framework], IWDTFSystemAction2 interface, Microsoft.WDTF.IWDTFSystemAction2.IsRestarted, Microsoft::WDTF::IWDTFSystemAction2::IsRestarted, dtf.iwdtfsystemaction2_isrestarted, get_IsRestarted,IWDTFSystemAction2.get_IsRestarted, wdtfsystemaction/IWDTFSystemAction2::IsRestarted, wdtfsystemaction/IWDTFSystemAction2::get_IsRestarted
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.IsRestarted
-	IWDTFSystemAction2.get_IsRestarted
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::get_IsRestarted method


## -description


Gets a value that indicates whether the test script restarted as a result of a call to 
	<a href="https://msdn.microsoft.com/library/windows/hardware/hh439319">RebootRestart</a> or 
	<a href="https://msdn.microsoft.com/library/windows/hardware/hh439321">RebootRestartWithContext</a>.

This property is read-only.


## -syntax


````
HRESULT get_IsRestarted(
  [out, retval] VARIANT_BOOL *pbIsRestarted
);
````


## -parameters


## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::IsRestarted property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


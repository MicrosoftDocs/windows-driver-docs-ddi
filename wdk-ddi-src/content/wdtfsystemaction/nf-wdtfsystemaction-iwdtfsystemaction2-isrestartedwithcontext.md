---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.IsRestartedWithContext
title: IWDTFSystemAction2::IsRestartedWithContext method
author: windows-driver-content
description: Gets a value that indicates whether the test script was restarted for a specific context.
old-location: dtf\iwdtfsystemaction2_isrestartedwithcontext.htm
old-project: dtf
ms.assetid: 4a7038e6-4c56-48cb-ae8b-34acc363a9a9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], IsRestartedWithContext method, IWDTFSystemAction2::IsRestartedWithContext, IsRestartedWithContext method [Windows Device Testing Framework], IsRestartedWithContext method [Windows Device Testing Framework], IWDTFSystemAction2 interface, IsRestartedWithContext,IWDTFSystemAction2.IsRestartedWithContext, Microsoft.WDTF.IWDTFSystemAction2.IsRestartedWithContext, Microsoft::WDTF::IWDTFSystemAction2::IsRestartedWithContext, dtf.iwdtfsystemaction2_isrestartedwithcontext, wdtfsystemaction/IWDTFSystemAction2::IsRestartedWithContext
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
req.lib: 
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
-	IWDTFSystemAction2.IsRestartedWithContext
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::IsRestartedWithContext method


## -description


Gets a value that indicates whether the test script was restarted for a specific context.


## -parameters




### -param psContextName




### -param pbIsRestarted [out, retval]

True if the script was restarted with the context; otherwise, false.


#### - psContext [in]

The context name.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::IsRestartedWithContext method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


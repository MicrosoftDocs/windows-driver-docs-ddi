---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.IsRestartedWithContext
title: IWDTFSystemAction2::IsRestartedWithContext (wdtfsystemaction.h)
description: Gets a value that indicates whether the test script was restarted for a specific context.
old-location: dtf\iwdtfsystemaction2_isrestartedwithcontext.htm
tech.root: dtf
ms.assetid: 4a7038e6-4c56-48cb-ae8b-34acc363a9a9
ms.date: 04/04/2018
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],IsRestartedWithContext method, IWDTFSystemAction2.IsRestartedWithContext, IWDTFSystemAction2::IsRestartedWithContext, IsRestartedWithContext, IsRestartedWithContext method [Windows Device Testing Framework], IsRestartedWithContext method [Windows Device Testing Framework],IWDTFSystemAction2 interface, Microsoft.WDTF.IWDTFSystemAction2.IsRestartedWithContext, Microsoft::WDTF::IWDTFSystemAction2::IsRestartedWithContext, dtf.iwdtfsystemaction2_isrestartedwithcontext, wdtfsystemaction/IWDTFSystemAction2::IsRestartedWithContext
ms.topic: method
f1_keywords:
 - "wdtfsystemaction/IWDTFSystemAction2.IsRestartedWithContext"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFSystemAction.Interop.dll
api_name:
- IWDTFSystemAction2.IsRestartedWithContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSystemAction2::IsRestartedWithContext


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




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>
 

 


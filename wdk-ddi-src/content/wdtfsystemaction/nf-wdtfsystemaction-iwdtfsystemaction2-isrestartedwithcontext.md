---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.IsRestartedWithContext
title: IWDTFSystemAction2::IsRestartedWithContext (wdtfsystemaction.h)
description: Gets a value that indicates whether the test script was restarted for a specific context.
old-location: dtf\iwdtfsystemaction2_isrestartedwithcontext.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::IsRestartedWithContext"]
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],IsRestartedWithContext method, IWDTFSystemAction2.IsRestartedWithContext, IWDTFSystemAction2::IsRestartedWithContext, IsRestartedWithContext, IsRestartedWithContext method [Windows Device Testing Framework], IsRestartedWithContext method [Windows Device Testing Framework],IWDTFSystemAction2 interface, Microsoft.WDTF.IWDTFSystemAction2.IsRestartedWithContext, Microsoft::WDTF::IWDTFSystemAction2::IsRestartedWithContext, dtf.iwdtfsystemaction2_isrestartedwithcontext, wdtfsystemaction/IWDTFSystemAction2::IsRestartedWithContext
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSystemAction2::IsRestartedWithContext
 - wdtfsystemaction/IWDTFSystemAction2::IsRestartedWithContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFSystemAction.Interop.dll
api_name:
 - IWDTFSystemAction2::IsRestartedWithContext
---

# IWDTFSystemAction2::IsRestartedWithContext


## -description

Gets a value that indicates whether the test script was restarted for a specific context.

## -parameters

### -param psContextName

### -param pbIsRestarted 

[out, retval]
True if the script was restarted with the context; otherwise, false.


#### - psContext [in]

The context name.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>


---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.RebootRestartWithContext
title: IWDTFSystemAction2::RebootRestartWithContext (wdtfsystemaction.h)
description: Reboots the system and restarts the test script with context data.
old-location: dtf\iwdtfsystemaction2_rebootrestartwithcontext.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::RebootRestartWithContext"]
ms.keywords: IWDTFSystemAction2 interface [Windows Device Testing Framework],RebootRestartWithContext method, IWDTFSystemAction2.RebootRestartWithContext, IWDTFSystemAction2::RebootRestartWithContext, Microsoft.WDTF.IWDTFSystemAction2.RebootRestartWithContext, Microsoft::WDTF::IWDTFSystemAction2::RebootRestartWithContext, RebootRestartWithContext, RebootRestartWithContext method [Windows Device Testing Framework], RebootRestartWithContext method [Windows Device Testing Framework],IWDTFSystemAction2 interface, dtf.iwdtfsystemaction2_rebootrestartwithcontext, wdtfsystemaction/IWDTFSystemAction2::RebootRestartWithContext
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSystemAction2::RebootRestartWithContext
 - wdtfsystemaction/IWDTFSystemAction2::RebootRestartWithContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFSystemAction.Interop.dll
api_name:
 - IWDTFSystemAction2::RebootRestartWithContext
---

# IWDTFSystemAction2::RebootRestartWithContext


## -description

Reboots the  system and restarts the test script with context data.

## -parameters

### -param psContextName

#### - psContext [in]

The context name.


#### - psContextData [in]

The context data.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>


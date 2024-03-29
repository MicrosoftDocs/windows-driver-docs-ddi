---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.GetNextSleepState
title: IWDTFSystemAction2::GetNextSleepState (wdtfsystemaction.h)
description: Returns the next supported sleep state.
old-location: dtf\iwdtfsystemaction2_getnextsleepstate.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSystemAction2::GetNextSleepState"]
ms.keywords: GetNextSleepState, GetNextSleepState method [Windows Device Testing Framework], GetNextSleepState method [Windows Device Testing Framework],IWDTFSystemAction2 interface, IWDTFSystemAction2 interface [Windows Device Testing Framework],GetNextSleepState method, IWDTFSystemAction2.GetNextSleepState, IWDTFSystemAction2::GetNextSleepState, Microsoft.WDTF.IWDTFSystemAction2.GetNextSleepState, Microsoft::WDTF::IWDTFSystemAction2::GetNextSleepState, dtf.iwdtfsystemaction2_getnextsleepstate, wdtfsystemaction/IWDTFSystemAction2::GetNextSleepState
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
 - IWDTFSystemAction2::GetNextSleepState
 - wdtfsystemaction/IWDTFSystemAction2::GetNextSleepState
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WDTFSystemAction.Interop.dll
api_name:
 - IWDTFSystemAction2::GetNextSleepState
---

# IWDTFSystemAction2::GetNextSleepState


## -description

Returns the next supported sleep state.

## -parameters

### -param pnSleepState [out, retval]


The sleep state.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdtfsystemaction/nn-wdtfsystemaction-iwdtfsystemaction2">IWDTFSystemAction2</a>


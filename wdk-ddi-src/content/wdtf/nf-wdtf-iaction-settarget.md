---
UID: NF:wdtf.IAction.SetTarget
title: IAction::SetTarget (wdtf.h)
description: The SetTarget method is used internally by WDTF. Do not call this method directly.
old-location: dtf\iaction_settarget.htm
tech.root: dtf
ms.assetid: ac539b82-83a1-4ccb-8088-c6f4b746a184
ms.date: 04/04/2018
ms.keywords: IAction interface [Windows Device Testing Framework],SetTarget method, IAction.SetTarget, IAction::SetTarget, IAction_6b35121b-1750-475f-8c37-5edf9c0b8585.xml, Microsoft.WDTF.IAction.SetTarget, Microsoft::WDTF::IAction::SetTarget, SetTarget, SetTarget method [Windows Device Testing Framework], SetTarget method [Windows Device Testing Framework],IAction interface, dtf.iaction_settarget, wdtf/IAction::SetTarget
ms.topic: method
f1_keywords:
 - "wdtf/IAction.SetTarget"
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTF.Interop.metadata_dll.dll
api_name:
- IAction.SetTarget
product:
- Windows
targetos: Windows
req.typenames: 
---

# IAction::SetTarget


## -description


The <b>SetTarget</b> method is used internally by WDTF. Do not call this method directly.


## -parameters




### -param pMainTarget [in]

The main target for the implementation to use. This target is the one 
that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a> was called on.


### -param MoreTargets [in]

Optional additional targets for the implementation. Currently, the <i>MoreTargets</i> parameter will always be VT_EMPTY. You should fail the <b>SetTarget</b> call if this parameter is anything other than VT_EMPTY.  


## -returns



<b>SetTarget</b> returns a standard <b>HRESULT</b> value




## -remarks



The <b>SetTarget</b> method is used when you are creating WDTF actions.  Do not call this method from a WDTF scenario.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Action interfaces</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iaction">IAction</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftarget2">IWDTFTarget2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nf-wdtf-iwdtftarget2-getinterface">IWDTFTarget2::GetInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtf/nn-wdtf-iwdtftargets2">IWDTFTargets2</a>
 

 


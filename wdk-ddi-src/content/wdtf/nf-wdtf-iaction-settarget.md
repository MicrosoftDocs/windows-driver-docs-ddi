---
UID: NF:wdtf.IAction.SetTarget
title: IAction::SetTarget method
author: windows-driver-content
description: The SetTarget method is used internally by WDTF. Do not call this method directly.
old-location: dtf\iaction_settarget.htm
old-project: dtf
ms.assetid: ac539b82-83a1-4ccb-8088-c6f4b746a184
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, A, I, IAction, IAction interface [Windows Device Testing Framework], SetTarget method, IAction::SetTarget, IAction_6b35121b-1750-475f-8c37-5edf9c0b8585.xml, Microsoft.WDTF.IAction.SetTarget, Microsoft::WDTF::IAction::SetTarget, S, SetTarget method [Windows Device Testing Framework], SetTarget method [Windows Device Testing Framework], IAction interface, SetTarget,IAction.SetTarget, T, a, c, dtf.iaction_settarget, e, g, i, n, o, r, t, wdtf/IAction::SetTarget"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
req.lib: wdtf.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTF.Interop.metadata_dll.dll
apiname:
-	IAction.SetTarget
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IAction::SetTarget method


## -description


The <b>SetTarget</b> method is used internally by WDTF. Do not call this method directly.


## -syntax


````
HRESULT SetTarget(
  [in] IWDTFTarget2 *pMainTarget,
  [in] VARIANT      MoreTargets
);
````


## -parameters




### -param pMainTarget [in]

The main target for the implementation to use. This target is the one 
that <a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a> was called on.


### -param MoreTargets [in]

Optional additional targets for the implementation. Currently, the <i>MoreTargets</i> parameter will always be VT_EMPTY. You should fail the <b>SetTarget</b> call if this parameter is anything other than VT_EMPTY.  


## -returns



<b>SetTarget</b> returns a standard <b>HRESULT</b> value




## -remarks



The <b>SetTarget</b> method is used when you are creating WDTF actions.  Do not call this method from a WDTF scenario.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



<a href="..\wdtf\nn-wdtf-iaction.md">IAction</a>



<a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538355">Action interfaces</a>



<a href="https://msdn.microsoft.com/dddd631e-7ccf-4554-9236-b567c5108fe2">IWDTFTarget2::GetInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IAction::SetTarget method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


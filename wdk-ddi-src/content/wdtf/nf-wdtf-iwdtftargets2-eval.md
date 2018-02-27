---
UID: NF:wdtf.IWDTFTargets2.Eval
title: IWDTFTargets2::Eval method
author: windows-driver-content
description: Evaluates whether all items in the collection match an SDEL statement.
old-location: dtf\iwdtftargets2_eval.htm
old-project: dtf
ms.assetid: 028a1fa9-686d-4f56-a49f-a7e90f960018
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: Eval method [Windows Device Testing Framework], Eval method [Windows Device Testing Framework], IWDTFTargets2 interface, Eval,IWDTFTargets2.Eval, IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], Eval method, IWDTFTargets2::Eval, Microsoft.WDTF.IWDTFTargets2.Eval, Microsoft::WDTF::IWDTFTargets2::Eval, dtf.iwdtftargets2_eval, wdtf/IWDTFTargets2::Eval
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
-	IWDTFTargets2.Eval
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTargets2::Eval method


## -description


Evaluates whether all items in the collection match an SDEL statement.


## -syntax


````
HRESULT Eval(
  [in]          BSTR         SDEL,
  [out, retval] VARIANT_BOOL *pResult
);
````


## -parameters




### -param SDEL [in]

The SDEL query string.


### -param pResult [out, retval]

True if all items match; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftargets2.md">IWDTFTargets2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTargets2::Eval method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


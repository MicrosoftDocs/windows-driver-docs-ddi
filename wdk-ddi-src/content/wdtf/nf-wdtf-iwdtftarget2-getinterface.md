---
UID: NF:wdtf.IWDTFTarget2.GetInterface
title: IWDTFTarget2::GetInterface method
author: windows-driver-content
description: Returns an action for the target.
old-location: dtf\iwdtftarget2_getinterface.htm
old-project: dtf
ms.assetid: dddd631e-7ccf-4554-9236-b567c5108fe2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., 2, :, D, F, G, GetInterface method [Windows Device Testing Framework], GetInterface method [Windows Device Testing Framework], IWDTFTarget2 interface, GetInterface,IWDTFTarget2.GetInterface, I, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], GetInterface method, IWDTFTarget2::GetInterface, Microsoft.WDTF.IWDTFTarget2.GetInterface, Microsoft::WDTF::IWDTFTarget2::GetInterface, T, W, a, c, dtf.iwdtftarget2_getinterface, e, f, g, n, r, t, wdtf/IWDTFTarget2::GetInterface"
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
-	IWDTFTarget2.GetInterface
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::GetInterface method


## -description


Returns an action for the target.


## -syntax


````
HRESULT GetInterface(
  [in]           BSTR         ProgID,
  [in, optional] VARIANT      MoreTargets,
  [in, optional] VARIANT      MonikerSuffix,
  [out, retval]  IWDTFAction2 **ppInterface
);
````


## -parameters




### -param WDTFInterfaceName




### -param Args




### -param MonikerSuffix [in, optional]

An optional moniker that defines more options about how 
the interface should be instantiated. 

This parameter is not yet implemented. 
Set <i>MonikerSuffix </i>to a <b>VARIANT</b> that 
contains <b>VT_EMPTY</b>.


### -param ppInterface [out, retval]

The address of a variable that will receive the action.


#### - ProgID [in]

The WDTF ProgID of the requested interface.


#### - MoreTargets [in, optional]

Optional extra arguments that you can use to 
define additional targets to attach to the returned interface. 

This parameter is not 
currently implemented. Set <i>MoreTargets</i> to a <b>VARIANT</b> 
that contains <b>VT_EMPTY</b>.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



The <b>GetInterface</b> method is the most useful method in the WDTF object model. 
<b>GetInterface</b> enables you to simply locate a target-specific 
implementation of an action interface without caring about the specifics of the target.

To write a WDTF scenario, you must understand both the syntax and the semantics of the 
requested action interface. 

For more information about the <b>GetInterface</b> method, 
see <a href="https://msdn.microsoft.com/b329e9a2-7d24-4612-9aa1-9d7955a61473">Controlling Targets</a>.

For detailed descriptions of the interfaces that WDTF includes, 
see <a href="https://msdn.microsoft.com/library/windows/hardware/ff538355">Action Interfaces</a>.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtftarget2.md">IWDTFTarget2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFTarget2::GetInterface method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


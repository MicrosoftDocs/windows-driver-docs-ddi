---
UID: NF:wdtf.IWDTFTarget2.GetInterface
title: IWDTFTarget2::GetInterface
author: windows-driver-content
description: Returns an action for the target.
old-location: dtf\iwdtftarget2_getinterface.htm
tech.root: dtf
ms.assetid: dddd631e-7ccf-4554-9236-b567c5108fe2
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: GetInterface, GetInterface method [Windows Device Testing Framework], GetInterface method [Windows Device Testing Framework],IWDTFTarget2 interface, IWDTFTarget2 interface [Windows Device Testing Framework],GetInterface method, IWDTFTarget2.GetInterface, IWDTFTarget2::GetInterface, Microsoft.WDTF.IWDTFTarget2.GetInterface, Microsoft::WDTF::IWDTFTarget2::GetInterface, dtf.iwdtftarget2_getinterface, wdtf/IWDTFTarget2::GetInterface
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFTarget2.GetInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFTarget2::GetInterface


## -description


Returns an action for the target.


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


#### - MoreTargets [in, optional]

Optional extra arguments that you can use to 
define additional targets to attach to the returned interface. 

This parameter is not 
currently implemented. Set <i>MoreTargets</i> to a <b>VARIANT</b> 
that contains <b>VT_EMPTY</b>.


#### - ProgID [in]

The WDTF ProgID of the requested interface.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>
 

 


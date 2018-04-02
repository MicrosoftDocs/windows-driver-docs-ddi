---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.RebootRestartWithContext
title: IWDTFSystemAction2::RebootRestartWithContext method
author: windows-driver-content
description: Reboots the system and restarts the test script with context data.
old-location: dtf\iwdtfsystemaction2_rebootrestartwithcontext.htm
old-project: dtf
ms.assetid: d88fe083-328c-4ce4-bb15-9fa824384f57
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], RebootRestartWithContext method, IWDTFSystemAction2::RebootRestartWithContext, Microsoft.WDTF.IWDTFSystemAction2.RebootRestartWithContext, Microsoft::WDTF::IWDTFSystemAction2::RebootRestartWithContext, RebootRestartWithContext method [Windows Device Testing Framework], RebootRestartWithContext method [Windows Device Testing Framework], IWDTFSystemAction2 interface, RebootRestartWithContext,IWDTFSystemAction2.RebootRestartWithContext, dtf.iwdtfsystemaction2_rebootrestartwithcontext, wdtfsystemaction/IWDTFSystemAction2::RebootRestartWithContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.RebootRestartWithContext
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::RebootRestartWithContext method


## -description


Reboots the  system and restarts the test script with context data.


## -parameters




### -param psContextName






#### - psContext [in]

The context name.


#### - psContextData [in]

The context data.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>
 

 


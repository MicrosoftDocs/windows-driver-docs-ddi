---
UID: NF:wdtf.IWDTFTarget2.HasContext
title: IWDTFTarget2::HasContext method
author: windows-driver-content
description: Determines whether a given context exists for the target.
old-location: dtf\iwdtftarget2_hascontext.htm
old-project: dtf
ms.assetid: 16ea6100-6e3e-4e50-9055-4396deb39a37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: HasContext method [Windows Device Testing Framework], HasContext method [Windows Device Testing Framework], IWDTFTarget2 interface, HasContext,IWDTFTarget2.HasContext, IWDTFTarget2, IWDTFTarget2 interface [Windows Device Testing Framework], HasContext method, IWDTFTarget2::HasContext, Microsoft.WDTF.IWDTFTarget2.HasContext, Microsoft::WDTF::IWDTFTarget2::HasContext, dtf.iwdtftarget2_hascontext, wdtf/IWDTFTarget2::HasContext
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
-	IWDTFTarget2.HasContext
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFTarget2::HasContext method


## -description


Determines whether a given context exists for the target.


## -parameters




### -param Tag [in]

The context name.


### -param pResult [out, retval]

True if the named context exists; otherwise, false.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a>
 

 


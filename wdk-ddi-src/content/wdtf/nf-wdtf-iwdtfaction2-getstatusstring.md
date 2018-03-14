---
UID: NF:wdtf.IWDTFAction2.GetStatusString
title: IWDTFAction2::GetStatusString method
author: windows-driver-content
description: Returns the status for the last operation as a string.
old-location: dtf\iwdtfaction2_getstatusstring.htm
old-project: dtf
ms.assetid: 21f7a3ea-5db9-4666-865c-c6b1ca9ba20f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetStatusString method [Windows Device Testing Framework], GetStatusString method [Windows Device Testing Framework], IWDTFAction2 interface, GetStatusString,IWDTFAction2.GetStatusString, IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], GetStatusString method, IWDTFAction2::GetStatusString, Microsoft.WDTF.IWDTFAction2.GetStatusString, Microsoft::WDTF::IWDTFAction2::GetStatusString, dtf.iwdtfaction2_getstatusstring, wdtf/IWDTFAction2::GetStatusString
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
-	IWDTFAction2.GetStatusString
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFAction2::GetStatusString method


## -description


Returns the status for the last operation as a string.


## -syntax


````
HRESULT GetStatusString(
  [out, retval] BSTR *pResult
);
````


## -parameters




### -param pResult [out, retval]

The status for the last operation.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a>



 

 



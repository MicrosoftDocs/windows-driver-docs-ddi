---
UID: NF:wdtf.IWDTFLOG2.StartTestCase
title: IWDTFLOG2::StartTestCase method
author: windows-driver-content
description: Marks the start of a test case.
old-location: dtf\iwdtflog2_starttestcase.htm
old-project: dtf
ms.assetid: d72bff68-d1c0-4ce4-bc2d-abe350036eec
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., 2, :, C, D, F, G, I, IWDTFLOG2, IWDTFLOG2 interface [Windows Device Testing Framework], StartTestCase method, IWDTFLOG2::StartTestCase, L, Microsoft.WDTF.IWDTFLOG2.StartTestCase, Microsoft::WDTF::IWDTFLOG2::StartTestCase, O, S, StartTestCase method [Windows Device Testing Framework], StartTestCase method [Windows Device Testing Framework], IWDTFLOG2 interface, StartTestCase,IWDTFLOG2.StartTestCase, T, W, a, dtf.iwdtflog2_starttestcase, e, r, s, t, wdtf/IWDTFLOG2::StartTestCase"
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
-	IWDTFLOG2.StartTestCase
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFLOG2::StartTestCase method


## -description


Marks the start of a test case.


## -syntax


````
HRESULT StartTestCase(
  [in] BSTR sTestCaseName
);
````


## -parameters




### -param sTestCaseName [in]

The test case name.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtflog2.md">IWDTFLOG2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFLOG2::StartTestCase method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


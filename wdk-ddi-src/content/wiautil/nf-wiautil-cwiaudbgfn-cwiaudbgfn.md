---
UID: NF:wiautil.CWiauDbgFn.CWiauDbgFn
title: CWiauDbgFn::CWiauDbgFn method
author: windows-driver-content
description: The CWiauDbgFn::CWiauDbgFn method is used for tracing when a function or method is entered.
old-location: image\cwiaudbgfn_cwiaudbgfn.htm
old-project: image
ms.assetid: dbb367a7-d7e6-4081-9618-1c4e38cccd31
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: CWiauDbgFn, CWiauDbgFn method [Imaging Devices], image.cwiaudbgfn_cwiaudbgfn, wiautil/CWiauDbgFn::CWiauDbgFn, CWiauDbgFn interface [Imaging Devices], CWiauDbgFn method, CWiauDbgFn::CWiauDbgFn, CWiauDbgFn method [Imaging Devices], CWiauDbgFn interface, wiauFncs_1dfa7486-9ad3-41b8-8724-29165ea0a45b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wiautil.h
req.include-header: Wiautil.h, Wiamindr.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wiautil.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wiautil.h
apiname:
-	CWiauDbgFn.CWiauDbgFn
product: Windows
targetos: Windows
req.typenames: SKIP_AMOUNT
req.product: Windows 10 or later.
---

# CWiauDbgFn::CWiauDbgFn method


## -description


The <b>CWiauDbgFn::CWiauDbgFn</b> method is used for tracing when a function or method is entered.


## -syntax


````
void CWiauDbgFn(
   LPCSTR   fname
);
````


## -parameters




#### - fname

Specifies the name of the function or method being entered.


## -returns


This method does not return a value.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540356">CWiauDbgFn::~CWiauDbgFn</a>

<a href="..\wiautil\nl-wiautil-cwiaudbgfn.md">CWiauDbgFn</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20CWiauDbgFn::CWiauDbgFn method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


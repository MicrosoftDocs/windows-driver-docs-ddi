---
UID: NF:wdtf.IWDTFAction2.GetStatusString
title: IWDTFAction2::GetStatusString method
author: windows-driver-content
description: Returns the status for the last operation as a string.
old-location: dtf\iwdtfaction2_getstatusstring.htm
old-project: dtf
ms.assetid: 21f7a3ea-5db9-4666-865c-c6b1ca9ba20f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFAction2, IWDTFAction2 interface [Windows Device Testing Framework], GetStatusString method, GetStatusString, IWDTFAction2::GetStatusString, dtf.iwdtfaction2_getstatusstring, Microsoft::WDTF::IWDTFAction2::GetStatusString, Microsoft.WDTF.IWDTFAction2.GetStatusString, wdtf/IWDTFAction2::GetStatusString, GetStatusString method [Windows Device Testing Framework], IWDTFAction2 interface, GetStatusString method [Windows Device Testing Framework]
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
-	IWDTFAction2.GetStatusString
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFAction2::GetStatusString method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


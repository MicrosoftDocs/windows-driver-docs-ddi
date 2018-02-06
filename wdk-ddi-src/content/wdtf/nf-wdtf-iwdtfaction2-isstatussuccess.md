---
UID: NF:wdtf.IWDTFAction2.IsStatusSuccess
title: IWDTFAction2::IsStatusSuccess method
author: windows-driver-content
description: Gets a value that indicates whether the last operation was successful.
old-location: dtf\iwdtfaction2_isstatussuccess.htm
old-project: dtf
ms.assetid: c4e6f54f-815d-4ce1-93e1-b18663aab1b1
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWDTFAction2, IsStatusSuccess method [Windows Device Testing Framework], IWDTFAction2 interface, Microsoft::WDTF::IWDTFAction2::IsStatusSuccess, IsStatusSuccess method [Windows Device Testing Framework], Microsoft.WDTF.IWDTFAction2.IsStatusSuccess, IsStatusSuccess, wdtf/IWDTFAction2::IsStatusSuccess, dtf.iwdtfaction2_isstatussuccess, IWDTFAction2 interface [Windows Device Testing Framework], IsStatusSuccess method, IWDTFAction2::IsStatusSuccess
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
-	IWDTFAction2.IsStatusSuccess
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFAction2::IsStatusSuccess method


## -description


Gets a value that indicates whether the last operation was successful.


## -syntax


````
HRESULT IsStatusSuccess(
  [out, retval] VARIANT_BOOL *pResult
);
````


## -parameters




### -param pResult [out, retval]

True if the last operation was successful; otherwise, false.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\wdtf\nn-wdtf-iwdtfaction2.md">IWDTFAction2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFAction2::IsStatusSuccess method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


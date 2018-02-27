---
UID: NF:wdtf.IWDTFLongNumbers2.Remove
title: IWDTFLongNumbers2::Remove method
author: windows-driver-content
description: Removes a long number from the collection.
old-location: dtf\iwdtflongnumbers2_remove.htm
old-project: dtf
ms.assetid: b566eedc-2a04-497b-9491-7bd5768f0dce
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFLongNumbers2, IWDTFLongNumbers2 interface [Windows Device Testing Framework], Remove method, IWDTFLongNumbers2::Remove, Microsoft.WDTF.IWDTFLongNumbers2.Remove, Microsoft::WDTF::IWDTFLongNumbers2::Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework], IWDTFLongNumbers2 interface, Remove,IWDTFLongNumbers2.Remove, dtf.iwdtflongnumbers2_remove, wdtf/IWDTFLongNumbers2::Remove
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
-	IWDTFLongNumbers2.Remove
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFLongNumbers2::Remove method


## -description


Removes a long number from the collection.


## -syntax


````
HRESULT Remove(
  [in] LONG Index
);
````


## -parameters




### -param Index [in]

The 0-based index value of the number to remove.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtf\nn-wdtf-iwdtflongnumbers2.md">IWDTFLongNumbers2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFLongNumbers2::Remove method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


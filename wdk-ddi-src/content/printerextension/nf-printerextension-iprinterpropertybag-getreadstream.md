---
UID: NF:printerextension.IPrinterPropertyBag.GetReadStream
title: IPrinterPropertyBag::GetReadStream method
author: windows-driver-content
description: Gets a stream in order to read from a stream property.
old-location: print\iprinterpropertybag_getreadstream.htm
old-project: print
ms.assetid: BDA58F6A-A245-4616-866C-6D1734EFB469
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrinterPropertyBag::GetReadStream, GetReadStream method [Print Devices], GetReadStream, GetReadStream method [Print Devices], IPrinterPropertyBag interface, print.iprinterpropertybag_getreadstream, IPrinterPropertyBag, printerextension/IPrinterPropertyBag::GetReadStream, IPrinterPropertyBag interface [Print Devices], GetReadStream method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: Printerextension.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrinterPropertyBag.GetReadStream
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterPropertyBag::GetReadStream method


## -description


Gets a stream in order to read from a stream property.


## -syntax


````
HRESULT GetReadStream(
  [in]  BSTR    bstrName,
  [out] IStream **ppValueStream
);
````


## -parameters




### -param bstrName [in]

The property to read.


### -param ppValue






#### - ppValueStream [out]

The returned stream.


## -returns



This method returns an <b>HRESULT</b> value.




## -remarks



This method does not work with non-stream properties.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterpropertybag.md">IPrinterPropertyBag</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterPropertyBag::GetReadStream method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


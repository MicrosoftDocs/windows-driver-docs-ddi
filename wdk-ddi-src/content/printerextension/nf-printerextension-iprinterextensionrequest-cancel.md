---
UID: NF:printerextension.IPrinterExtensionRequest.Cancel
title: IPrinterExtensionRequest::Cancel method
author: windows-driver-content
description: Completes the extension event with a cancellation.
old-location: print\iprinterextensionrequest_cancel.htm
old-project: print
ms.assetid: CE5C2999-37D7-4702-B94D-E3131AE34E78
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrinterExtensionRequest, IPrinterExtensionRequest::Cancel, Cancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterExtensionRequest.Cancel
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionRequest::Cancel method



## -description
Completes the extension event with a cancellation.



## -syntax

````
HRESULT Cancel(
  [in] HRESULT hr,
  [in] BSTR    bstrLogMessage
);
````


## -parameters

### -param hr [in]

The operation result.


### -param bstrLogMessage [in]

The log message.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionRequest::Cancel method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


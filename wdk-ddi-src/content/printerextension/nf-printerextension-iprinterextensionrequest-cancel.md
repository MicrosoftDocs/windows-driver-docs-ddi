---
UID: NF:printerextension.IPrinterExtensionRequest.Cancel
title: IPrinterExtensionRequest::Cancel method
author: windows-driver-content
description: Completes the extension event with a cancellation.
old-location: print\iprinterextensionrequest_cancel.htm
old-project: print
ms.assetid: CE5C2999-37D7-4702-B94D-E3131AE34E78
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Cancel method [Print Devices], Cancel method [Print Devices], IPrinterExtensionRequest interface, Cancel,IPrinterExtensionRequest.Cancel, IPrinterExtensionRequest, IPrinterExtensionRequest interface [Print Devices], Cancel method, IPrinterExtensionRequest::Cancel, print.iprinterextensionrequest_cancel, printerextension/IPrinterExtensionRequest::Cancel
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterExtensionRequest.Cancel
product: Windows
targetos: Windows
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




### -param hrStatus




### -param bstrLogMessage [in]

The log message.


#### - hr [in]

The operation result.


## -returns



This method returns an <b>HRESULT</b> value.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensionrequest.md">IPrinterExtensionRequest</a>



 

 



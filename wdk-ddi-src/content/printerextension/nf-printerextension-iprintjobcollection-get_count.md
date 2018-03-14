---
UID: NF:printerextension.IPrintJobCollection.get_Count
title: IPrintJobCollection::get_Count method
author: windows-driver-content
description: Gets a count of the number of IPrinterExtensionContext objects in the collection.
old-location: print\iprinterextensioncontextcollection_count.htm
old-project: print
ms.assetid: F2279727-168D-451B-8EDB-8A4A36ACA08F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Count property [Print Devices], Count property [Print Devices], IPrinterExtensionContextCollection interface, IPrintJobCollection, IPrintJobCollection::get_Count, IPrinterExtensionContextCollection interface [Print Devices], Count property, IPrinterExtensionContextCollection.Count, IPrinterExtensionContextCollection::get_Count, get_Count, get_Count,IPrintJobCollection.get_Count, print.iprinterextensioncontextcollection_count, printerextension/IPrinterExtensionContextCollection::Count, printerextension/IPrinterExtensionContextCollection::get_Count
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	IPrinterExtensionContextCollection.Count
-	IPrinterExtensionContextCollection.get_Count
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJobCollection::get_Count method


## -description


Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a> objects in the collection.

This property is read-only.


## -syntax


````
HRESULT get_Count(
  [out, retval] ULONG *pulCount
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a>



<a href="..\printerextension\nn-printerextension-iprinterextensioncontext.md">IPrinterExtensionContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContextCollection::Count property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


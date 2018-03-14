---
UID: NF:printerextension.IPrinterExtensionContextCollection.get__NewEnum
title: IPrinterExtensionContextCollection::get__NewEnum method
author: windows-driver-content
description: Gets a pointer to the enumerants of IPrinterExtensionContextCollection objects.
old-location: print\iprinterextensioncontextcollection_newenum.htm
old-project: print
ms.assetid: 139B2E3F-AA08-4400-9BBF-A549B9EB2643
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], NewEnum method, IPrinterExtensionContextCollection,get_NewEnum, NewEnum, IPrinterExtensionContextCollection::NewEnum, IPrinterExtensionContextCollection::get__NewEnum, NewEnum method [Print Devices], NewEnum method [Print Devices], IPrinterExtensionContextCollection interface, get__NewEnum,IPrinterExtensionContextCollection.get__NewEnum, print.iprinterextensioncontextcollection_newenum, printerextension/IPrinterExtensionContextCollection::NewEnum
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
-	IPrinterExtensionContextCollection.NewEnum
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterExtensionContextCollection::get__NewEnum method


## -description


Gets a pointer to the enumerants of <a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a> objects.


## -syntax


````
HRESULT NewEnum(
  [out, retval] IUnknown **ppUnk
);
````


## -parameters




### -param ppUnk [out, retval]


## -returns



Returns an <b>HRESULT</b> value. If the property call was not successful,  it returns the appropriate <b>HRESULT</b> error code.




## -see-also

<a href="..\printerextension\nn-printerextension-iprinterextensioncontextcollection.md">IPrinterExtensionContextCollection</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionContextCollection::NewEnum method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


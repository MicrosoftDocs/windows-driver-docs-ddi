---
UID: NF:printerextension.IPrintSchemaOptionCollection.GetAt
title: IPrintSchemaOptionCollection::GetAt method
author: windows-driver-content
description: Gets a pointer to an IPrintSchemaOption object.
old-location: print\iprintschemaoptioncollection_getat.htm
old-project: print
ms.assetid: B77297BF-09F7-46BD-A75F-D36E5E233E05
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetAt, print.iprintschemaoptioncollection_getat, GetAt method [Print Devices], IPrintSchemaOptionCollection::GetAt, IPrintSchemaOptionCollection, IPrintSchemaOptionCollection interface [Print Devices], GetAt method, printerextension/IPrintSchemaOptionCollection::GetAt, GetAt method [Print Devices], IPrintSchemaOptionCollection interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrintSchemaOptionCollection.GetAt
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaOptionCollection::GetAt method


## -description


Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.


## -syntax


````
HRESULT GetAt(
  [in]                    ULONG              ulIndex,
  [out, retval, optional] IPrintSchemaOption **ppOption
);
````


## -parameters




### -param ulIndex [in]

Index of the <b>IPrintSchemaOption</b> object within the collection.


### -param ppOption [out, retval, optional]

Pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.


## -returns


Returns an <b>HRESULT</b> value. If the method call was not successful,  it returns the appropriate <b>HRESULT</b> error code.



## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemaoptioncollection.md">IPrintSchemaOptionCollection</a>

<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaOptionCollection::GetAt method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


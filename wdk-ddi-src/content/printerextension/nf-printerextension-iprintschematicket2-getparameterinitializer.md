---
UID: NF:printerextension.IPrintSchemaTicket2.GetParameterInitializer
title: IPrintSchemaTicket2::GetParameterInitializer method
author: windows-driver-content
description: The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the &lt;psf:ParameterInit&gt; element in the PrintTicket XML.
old-location: print\iprintschematicket2_getparameterinitializer.htm
old-project: print
ms.assetid: E5403359-A757-4530-B17B-C80E8A45AA92
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetParameterInitializer method [Print Devices], GetParameterInitializer, print.iprintschematicket2_getparameterinitializer, IPrintSchemaTicket2, IPrintSchematicket2::GetParameterInitializer, GetParameterInitializer method [Print Devices], IPrintSchematicket2 interface, printerextension/IPrintSchematicket2::GetParameterInitializer, IPrintSchemaTicket2::GetParameterInitializer, IPrintSchematicket2 interface [Print Devices], GetParameterInitializer method
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
-	IPrintSchematicket2.GetParameterInitializer
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaTicket2::GetParameterInitializer method


## -description


The <b>GetParameterInitializer</b> method retrieves the <a href="..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md">IPrintSchemaParameterInitializer</a> object, and it  represents the &lt;psf:ParameterInit&gt; element in the PrintTicket XML.

The keyword name and keyword namespace URI specify the <b>IPrintSchemaParameterInitializer</b> object to be retrieved.


## -syntax


````
HRESULT GetParameterInitializer(
  [in]          BSTR                             bstrName,
  [in]          BSTR                             bstrNamespaceUri,
  [out, retval] IPrintSchemaParameterInitializer **ppParameterInitializer
);
````


## -parameters




### -param bstrName [in]

The keyword name.


### -param bstrNamespaceUri [in]

The keyword namespace URI.


### -param ppParameterInitializer [out, retval]

The <a href="..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md">IPrintSchemaParameterInitializer</a> object.


## -returns


The <b>GetParameterInitializer</b> method returns an <b>HRESULT</b> value. If the property call was not successful, it returns the appropriate <b>HRESULT</b> error code.



## -see-also

<a href="..\printerextension\nn-printerextension-iprintschematicket2.md">IPrintSchematicket2</a>

<a href="..\printerextension\nn-printerextension-iprintschemaparameterinitializer.md">IPrintSchemaParameterInitializer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchematicket2::GetParameterInitializer method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


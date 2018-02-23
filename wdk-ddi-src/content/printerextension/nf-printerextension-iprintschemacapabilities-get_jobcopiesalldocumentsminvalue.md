---
UID: NF:printerextension.IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue
title: IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue method
author: windows-driver-content
description: Gets the JobCopiesAllDocuments parameter minimum value.
old-location: print\iprintschemacapabilities_jobcopiesalldocumentsminvalue.htm
old-project: print
ms.assetid: 181D085C-65C5-4D7E-9A1B-8641CC9B799B
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue, print.iprintschemacapabilities_jobcopiesalldocumentsminvalue, IPrintSchemaCapabilities interface [Print Devices], JobCopiesAllDocumentsMinValue property, IPrintSchemaCapabilities, IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue, printerextension/IPrintSchemaCapabilities::JobCopiesAllDocumentsMinValue, JobCopiesAllDocumentsMinValue property [Print Devices], IPrintSchemaCapabilities interface, JobCopiesAllDocumentsMinValue property [Print Devices], IPrintSchemaCapabilities.JobCopiesAllDocumentsMinValue, get_JobCopiesAllDocumentsMinValue
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
-	IPrintSchemaCapabilities.JobCopiesAllDocumentsMinValue
-	IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMinValue
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMinValue method


## -description


Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.

This is the copy count minimum.

This property is read-only.


## -syntax


````
HRESULT get_JobCopiesAllDocumentsMinValue(
  [out, retval] ULONG *pulJobCopiesAllDocumentsMinValue 
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::JobCopiesAllDocumentsMinValue property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


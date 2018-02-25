---
UID: NF:printerextension.IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue
title: IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue method
author: windows-driver-content
description: Gets the JobCopiesAllDocuments parameter maximum value.
old-location: print\iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue.htm
old-project: print
ms.assetid: A0705B79-BD13-4AB7-8647-A7AF905B97CC
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, A, C, D, I, IPrintSchemaCapabilities, IPrintSchemaCapabilities interface [Print Devices], JobCopiesAllDocumentsMaxValue property, IPrintSchemaCapabilities.JobCopiesAllDocumentsMaxValue, IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue, J, JobCopiesAllDocumentsMaxValue property [Print Devices], JobCopiesAllDocumentsMaxValue property [Print Devices], IPrintSchemaCapabilities interface, M, P, S, V, _, a, b, c, e, g, get_JobCopiesAllDocumentsMaxValue, get_JobCopiesAllDocumentsMaxValue,IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue, h, i, l, m, n, o, p, print.iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue, printerextension/IPrintSchemaCapabilities::JobCopiesAllDocumentsMaxValue, printerextension/IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue, r, s, t, u, x"
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
-	IPrintSchemaCapabilities.JobCopiesAllDocumentsMaxValue
-	IPrintSchemaCapabilities.get_JobCopiesAllDocumentsMaxValue
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::get_JobCopiesAllDocumentsMaxValue method


## -description


Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.

This is the copy count maximum.

This property is read-only.


## -syntax


````
HRESULT get_JobCopiesAllDocumentsMaxValue(
  [out, retval] ULONG *pulJobCopiesAllDocumentsMaxValue
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::JobCopiesAllDocumentsMaxValue property%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


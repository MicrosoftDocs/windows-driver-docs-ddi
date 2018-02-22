---
UID: NF:printerextension.IPrintJob.get_Id
title: IPrintJob::get_Id method
author: windows-driver-content
description: Gets the print job identifier (ID).
old-location: print\iprintjob_id.htm
old-project: print
ms.assetid: 8354E38C-0A3D-48CB-9CA5-0DC0C01FDF17
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IPrintJob interface [Print Devices], Id property, IPrintJob::get_Id, get_Id, IPrintJob, printerextension/IPrintJob::Id, printerextension/IPrintJob::get_Id, Id property [Print Devices], IPrintJob interface, print.iprintjob_id, IPrintJob.Id, Id property [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintJob.Id
-	IPrintJob.get_Id
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_Id method


## -description


Gets the print job identifier (ID).

This property is read-only.


## -syntax


````
HRESULT get_Id(
  [out, retval] ULONG *pulID
);
````


## -parameters


## -remarks



You must not use the <b>IPrintJob::Id</b> property  to invoke spooler Job APIs. This property is only provided as a way for you to identify a particular job, and to help with ordering or sorting of the jobs in the job snapshot.




## -see-also

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::Id property%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:printerextension.IPrintJob.get_Status
title: IPrintJob::get_Status method
author: windows-driver-content
description: Gets the current status of the print job.
old-location: print\iprintjob_status.htm
old-project: print
ms.assetid: 3C806C3B-78A1-44B6-A9AC-E7258D216637
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintjob_status, IPrintJob, IPrintJob interface [Print Devices], Status property, printerextension/IPrintJob::Status, Status property [Print Devices], IPrintJob interface, IPrintJob::get_Status, printerextension/IPrintJob::get_Status, get_Status, Status property [Print Devices], IPrintJob.Status
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
-	IPrintJob.Status
-	IPrintJob.get_Status
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_Status method


## -description


Gets the current status of the print job.

This property is read-only.


## -syntax


````
HRESULT get_Status(
  [out, retval] PrintJobStatus *pStatus
);
````


## -parameters


## -see-also

<a href="..\printerextension\ne-printerextension-tagprintjobstatus.md">PrintJobStatus</a>



<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::Status property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


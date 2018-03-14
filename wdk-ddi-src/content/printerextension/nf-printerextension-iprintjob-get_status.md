---
UID: NF:printerextension.IPrintJob.get_Status
title: IPrintJob::get_Status method
author: windows-driver-content
description: Gets the current status of the print job.
old-location: print\iprintjob_status.htm
old-project: print
ms.assetid: 3C806C3B-78A1-44B6-A9AC-E7258D216637
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintJob, IPrintJob interface [Print Devices], Status property, IPrintJob.Status, IPrintJob::get_Status, Status property [Print Devices], Status property [Print Devices], IPrintJob interface, get_Status, get_Status,IPrintJob.get_Status, print.iprintjob_status, printerextension/IPrintJob::Status, printerextension/IPrintJob::get_Status
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
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

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



<a href="..\printerextension\ne-printerextension-tagprintjobstatus.md">PrintJobStatus</a>



 

 



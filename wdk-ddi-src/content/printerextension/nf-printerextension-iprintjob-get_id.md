---
UID: NF:printerextension.IPrintJob.get_Id
title: IPrintJob::get_Id
author: windows-driver-content
description: Gets the print job identifier (ID).
old-location: print\iprintjob_id.htm
tech.root: print
ms.assetid: 8354E38C-0A3D-48CB-9CA5-0DC0C01FDF17
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintJob interface [Print Devices],Id property, IPrintJob.Id, IPrintJob.get_Id, IPrintJob::Id, IPrintJob::get_Id, Id property [Print Devices], Id property [Print Devices],IPrintJob interface, get_Id, print.iprintjob_id, printerextension/IPrintJob::Id, printerextension/IPrintJob::get_Id
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
-	IPrintJob.Id
-	IPrintJob.get_Id
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintJob::get_Id


## -description


Gets the print job identifier (ID).

This property is read-only.


## -parameters


## -remarks



You must not use the <b>IPrintJob::Id</b> property  to invoke spooler Job APIs. This property is only provided as a way for you to identify a particular job, and to help with ordering or sorting of the jobs in the job snapshot.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265396">IPrintJob</a>
 

 


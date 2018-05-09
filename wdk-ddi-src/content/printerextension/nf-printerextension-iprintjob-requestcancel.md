---
UID: NF:printerextension.IPrintJob.RequestCancel
title: IPrintJob::RequestCancel
author: windows-driver-content
description: Requests the cancellation of a print job.
old-location: print\iprintjob_requestcancel.htm
old-project: print
ms.assetid: 13F8A151-F28A-4A0F-B143-F3DB2197A36B
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintJob interface [Print Devices],RequestCancel method, IPrintJob.RequestCancel, IPrintJob::RequestCancel, RequestCancel, RequestCancel method [Print Devices], RequestCancel method [Print Devices],IPrintJob interface, print.iprintjob_requestcancel, printerextension/IPrintJob::RequestCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrintJob.RequestCancel
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintJob::RequestCancel


## -description


Requests the cancellation of a print job.


## -parameters






#### - void

None.


## -returns



Returns an <b>HRESULT</b> value. If the method call was not successful, it returns the appropriate <b>HRESULT</b> error code.




## -remarks



The <b>RequestCancel</b> method does not wait for the cancellation of a print job to be processed to completion before it returns.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265396">IPrintJob</a>
 

 


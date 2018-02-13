---
UID: NF:printerextension.IPrintJob.get_SubmissionTime
title: IPrintJob::get_SubmissionTime method
author: windows-driver-content
description: Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler).
old-location: print\iprintjob_submissiontime.htm
old-project: print
ms.assetid: 23433B59-A376-4D92-863E-4492621F3BF5
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: get_SubmissionTime, printerextension/IPrintJob::get_SubmissionTime, IPrintJob interface [Print Devices], SubmissionTime property, IPrintJob, print.iprintjob_submissiontime, IPrintJob::get_SubmissionTime, SubmissionTime property [Print Devices], IPrintJob interface, printerextension/IPrintJob::SubmissionTime, IPrintJob.SubmissionTime, SubmissionTime property [Print Devices]
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
-	IPrintJob.SubmissionTime
-	IPrintJob.get_SubmissionTime
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintJob::get_SubmissionTime method


## -description


Gets the submission time, in the “DATE” format, provided in the user’s local time (not in the UTC format that is provided by the spooler).

This property is read-only.


## -syntax


````
HRESULT get_SubmissionTime(
  [out, retval] DATE *pSubmissionTime
);
````


## -parameters


## -see-also

<a href="..\printerextension\nn-printerextension-iprintjob.md">IPrintJob</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintJob::SubmissionTime property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


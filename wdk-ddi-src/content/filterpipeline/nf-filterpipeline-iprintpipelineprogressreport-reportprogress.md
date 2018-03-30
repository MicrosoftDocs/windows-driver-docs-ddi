---
UID: NF:filterpipeline.IPrintPipelineProgressReport.ReportProgress
title: IPrintPipelineProgressReport::ReportProgress method
author: windows-driver-content
description: The ReportProgress method reports the progress of the XPS job consumption to the pipeline manager.
old-location: print\iprintpipelineprogressreport_reportprogress.htm
old-project: print
ms.assetid: 989e8888-3494-4355-a41f-2ed774a060d2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintPipelineProgressReport, IPrintPipelineProgressReport interface [Print Devices], ReportProgress method, IPrintPipelineProgressReport::ReportProgress, ReportProgress method [Print Devices], ReportProgress method [Print Devices], IPrintPipelineProgressReport interface, ReportProgress,IPrintPipelineProgressReport.ReportProgress, filterpipeline/IPrintPipelineProgressReport::ReportProgress, filterpipeline_3f4798ee-db6e-42ab-9eb8-fb016920fd08.xml, print.iprintpipelineprogressreport_reportprogress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
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
-	filterpipeline.h
api_name:
-	IPrintPipelineProgressReport.ReportProgress
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelineProgressReport::ReportProgress method


## -description


The <code>ReportProgress</code> method reports the progress of the XPS job consumption to the pipeline manager.


## -parameters




### -param update [in]

An <a href="https://msdn.microsoft.com/library/windows/hardware/ff548778">EXpsJobConsumption</a>-typed value that describes the progress to the pipeline manager.


## -returns



<code>ReportProgress</code> returns an <b>HRESULT</b> value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548778">EXpsJobConsumption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554314">IPrintPipelineProgressReport</a>
 

 


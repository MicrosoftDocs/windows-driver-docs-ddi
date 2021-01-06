---
UID: NF:filterpipeline.IPrintPipelineProgressReport.ReportProgress
title: IPrintPipelineProgressReport::ReportProgress (filterpipeline.h)
description: The ReportProgress method reports the progress of the XPS job consumption to the pipeline manager.
old-location: print\iprintpipelineprogressreport_reportprogress.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintPipelineProgressReport::ReportProgress"]
ms.keywords: IPrintPipelineProgressReport interface [Print Devices],ReportProgress method, IPrintPipelineProgressReport.ReportProgress, IPrintPipelineProgressReport::ReportProgress, ReportProgress, ReportProgress method [Print Devices], ReportProgress method [Print Devices],IPrintPipelineProgressReport interface, filterpipeline/IPrintPipelineProgressReport::ReportProgress, filterpipeline_3f4798ee-db6e-42ab-9eb8-fb016920fd08.xml, print.iprintpipelineprogressreport_reportprogress
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintPipelineProgressReport::ReportProgress
 - filterpipeline/IPrintPipelineProgressReport::ReportProgress
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintPipelineProgressReport.ReportProgress
---

# IPrintPipelineProgressReport::ReportProgress


## -description

The <code>ReportProgress</code> method reports the progress of the XPS job consumption to the pipeline manager.

## -parameters

### -param update 

[in]
An <a href="/windows-hardware/drivers/ddi/filterpipeline/ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003">EXpsJobConsumption</a>-typed value that describes the progress to the pipeline manager.

## -returns

<code>ReportProgress</code> returns an <b>HRESULT</b> value.

## -see-also

<a href="/windows-hardware/drivers/ddi/filterpipeline/ne-filterpipeline-__midl___midl_itf_filterpipeline_0000_0000_0003">EXpsJobConsumption</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelineprogressreport">IPrintPipelineProgressReport</a>

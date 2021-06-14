---
UID: NN:filterpipeline.IPrintPipelineProgressReport
title: IPrintPipelineProgressReport (filterpipeline.h)
description: A rendering filter uses the IPrintPipelineProgressReport interface to send progress status to a spooler.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintPipelineProgressReport interface"]
ms.keywords: IPrintPipelineProgressReport, IPrintPipelineProgressReport interface [Print Devices], IPrintPipelineProgressReport interface [Print Devices],described, filterpipeline/IPrintPipelineProgressReport, filterpipeline_de104fc6-8ac2-4a10-ab09-09596a093835.xml, print.iprintpipelineprogressreport
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintPipelineProgressReport
 - filterpipeline/IPrintPipelineProgressReport
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintPipelineProgressReport
---

# IPrintPipelineProgressReport interface

## -description

A rendering filter uses the **IPrintPipelineProgressReport** interface to send progress status to a spooler.

A rendering filter should search for the **XPS_FP_PROGRESS_REPORT** property in a property bag, get the progress, and then remove it from the property bag. If there are no rendering filters, the filter pipeline sends the notifications to the spooler. It is very important for a rendering filter to remove the progress and send progress status to the spooler; if progress status is not handled correctly, the spooler may get conflicting progress reports.

## -inheritance

The **IPrintPipelineProgressReport** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.

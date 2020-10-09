---
UID: NN:filterpipeline.IPrintPipelineProgressReport
title: IPrintPipelineProgressReport (filterpipeline.h)
description: A rendering filter uses the IPrintPipelineProgressReport interface to send progress status to a spooler.
old-location: print\iprintpipelineprogressreport.htm
tech.root: print
ms.assetid: 7a2644af-fdfe-4481-8c44-c40244b8a00e
ms.date: 04/20/2018
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

A rendering filter uses the <code>IPrintPipelineProgressReport</code> interface to send progress status to a spooler. 

A rendering filter should search for the <b>XPS_FP_PROGRESS_REPORT</b> property in a property bag, get the progress, and then remove it from the property bag. If there are no rendering filters, the filter pipeline sends the notifications to the spooler. It is very important for a rendering filter to remove the progress and send progress status to the spooler; if progress status is not handled correctly, the spooler may get conflicting progress reports.

## -inheritance

The <b xmlns:loc="https://microsoft.com/wdcml/l10n">IPrintPipelineProgressReport</b> interface inherits from the <a href="/windows/win32/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintPipelineProgressReport</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
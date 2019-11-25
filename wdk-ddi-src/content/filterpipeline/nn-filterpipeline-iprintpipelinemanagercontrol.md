---
UID: NN:filterpipeline.IPrintPipelineManagerControl
title: IPrintPipelineManagerControl (filterpipeline.h)
description: The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter::InitializeFilter method.
old-location: print\iprintpipelinemanagercontrol.htm
tech.root: print
ms.assetid: 82efbe8d-0928-4550-9de1-a806a00791eb
ms.date: 04/20/2018
ms.keywords: IPrintPipelineManagerControl, IPrintPipelineManagerControl interface [Print Devices], IPrintPipelineManagerControl interface [Print Devices],described, filterpipeline/IPrintPipelineManagerControl, filterpipeline_5b9732d1-6a75-4059-84fa-1bbbdeb70eb3.xml, print.iprintpipelinemanagercontrol
ms.topic: interface
f1_keywords:
 - "filterpipeline/IPrintPipelineManagerControl"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IPrintPipelineManagerControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelineManagerControl interface


## -description


The <code>IPrintPipelineManagerControl</code> interface is passed to each filter in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/filterpipeline/nf-filterpipeline-iprintpipelinefilter-initializefilter">IPrintPipelineFilter::InitializeFilter</a> method. Filters use this interface to:
<ul>
<li>
Request shutdown in low-memory situations.

</li>
<li>
Report when the filters are finished processing.

</li>
</ul>

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintPipelineManagerControl</b> interface inherits from the <a href="https://docs.microsoft.com/windows/desktop/api/unknwn/nn-unknwn-iunknown">IUnknown</a> interface. <b>IPrintPipelineManagerControl</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>


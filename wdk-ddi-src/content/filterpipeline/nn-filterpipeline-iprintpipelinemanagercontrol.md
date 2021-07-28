---
UID: NN:filterpipeline.IPrintPipelineManagerControl
title: IPrintPipelineManagerControl (filterpipeline.h)
description: The IPrintPipelineManagerControl interface is passed to each filter in the IPrintPipelineFilter::InitializeFilter method.
tech.root: print
ms.date: 06/11/2021
keywords: ["IPrintPipelineManagerControl interface"]
ms.keywords: IPrintPipelineManagerControl, IPrintPipelineManagerControl interface [Print Devices], IPrintPipelineManagerControl interface [Print Devices],described, filterpipeline/IPrintPipelineManagerControl, filterpipeline_5b9732d1-6a75-4059-84fa-1bbbdeb70eb3.xml, print.iprintpipelinemanagercontrol
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
 - IPrintPipelineManagerControl
 - filterpipeline/IPrintPipelineManagerControl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintPipelineManagerControl
---

# IPrintPipelineManagerControl interface

## -description

The **IPrintPipelineManagerControl** interface is passed to each filter in the [IPrintPipelineFilter::InitializeFilter](./nf-filterpipeline-iprintpipelinefilter-initializefilter.md) method. Filters use this interface to:

- Request shutdown in low-memory situations.

- Report when the filters are finished processing.

## -inheritance

The **IPrintPipelineManagerControl** interface inherits from the [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface.
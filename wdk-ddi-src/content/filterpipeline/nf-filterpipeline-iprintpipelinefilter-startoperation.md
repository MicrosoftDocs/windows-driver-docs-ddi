---
UID: NF:filterpipeline.IPrintPipelineFilter.StartOperation
title: IPrintPipelineFilter::StartOperation method
author: windows-driver-content
description: The StartOperation method starts the operation of a filter. The filter reads, processes, and writes data in this method.
old-location: print\iprintpipelinefilter_startoperation.htm
old-project: print
ms.assetid: 87139670-9b51-4ced-9624-2ec9f4726a84
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: StartOperation method [Print Devices], IPrintPipelineFilter interface, filterpipeline_9040ff14-d052-4360-bb31-b171581c14b6.xml, IPrintPipelineFilter, StartOperation, StartOperation method [Print Devices], IPrintPipelineFilter::StartOperation, print.iprintpipelinefilter_startoperation, filterpipeline/IPrintPipelineFilter::StartOperation, IPrintPipelineFilter interface [Print Devices], StartOperation method
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Filterpipeline.h
apiname:
-	IPrintPipelineFilter.StartOperation
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelineFilter::StartOperation method


## -description


The <code>StartOperation</code> method starts the operation of a filter. The filter reads, processes, and writes data in this method.


## -syntax


````
HRESULT STDMETHODCALLTYPE StartOperation(
    None
);
````


## -parameters






#### - None


## -returns



<code>StartOperation</code> returns an <b>HRESULT</b> value.




## -remarks



A filter returns the <code>StartOperation</code> call only when the filter processing is complete.




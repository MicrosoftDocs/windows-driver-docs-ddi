---
UID: NF:filterpipeline.IPrintPipelineManagerControl.FilterFinished
title: IPrintPipelineManagerControl::FilterFinished method
author: windows-driver-content
description: The FilterFinished method reports that a filter is finished processing.
old-location: print\iprintpipelinemanagercontrol_filterfinished.htm
old-project: print
ms.assetid: 6393b959-f67a-42e8-bb2b-e830bcf0d45f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintPipelineManagerControl, FilterFinished method [Print Devices], FilterFinished, filterpipeline_58038d61-195e-4144-adee-2615a62cef91.xml, filterpipeline/IPrintPipelineManagerControl::FilterFinished, IPrintPipelineManagerControl::FilterFinished, IPrintPipelineManagerControl interface [Print Devices], FilterFinished method, print.iprintpipelinemanagercontrol_filterfinished, FilterFinished method [Print Devices], IPrintPipelineManagerControl interface
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
-	IPrintPipelineManagerControl.FilterFinished
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelineManagerControl::FilterFinished method


## -description


The <code>FilterFinished</code> method reports that a filter is finished processing.


## -syntax


````
HRESULT STDMETHODCALLTYPE FilterFinished(
    None
);
````


## -parameters





#### - None



## -returns


<code>FilterFinished</code> returns an <b>HRESULT</b>.



## -remarks


The filter does not need to call the <code>FilterFinished</code> method. The filter pipeline assumes the filter has finished when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554301">IPrintPipelineFilter::StartOperation</a> method returns. <code>FilterFinished</code> is provided for compatibility and, when called, it does nothing but returns.



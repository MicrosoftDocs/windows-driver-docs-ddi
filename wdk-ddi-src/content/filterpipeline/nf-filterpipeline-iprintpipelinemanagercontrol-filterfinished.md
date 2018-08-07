---
UID: NF:filterpipeline.IPrintPipelineManagerControl.FilterFinished
title: IPrintPipelineManagerControl::FilterFinished
author: windows-driver-content
description: The FilterFinished method reports that a filter is finished processing.
old-location: print\iprintpipelinemanagercontrol_filterfinished.htm
tech.root: print
ms.assetid: 6393b959-f67a-42e8-bb2b-e830bcf0d45f
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: FilterFinished, FilterFinished method [Print Devices], FilterFinished method [Print Devices],IPrintPipelineManagerControl interface, IPrintPipelineManagerControl interface [Print Devices],FilterFinished method, IPrintPipelineManagerControl.FilterFinished, IPrintPipelineManagerControl::FilterFinished, filterpipeline/IPrintPipelineManagerControl::FilterFinished, filterpipeline_58038d61-195e-4144-adee-2615a62cef91.xml, print.iprintpipelinemanagercontrol_filterfinished
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
-	Filterpipeline.h
api_name:
-	IPrintPipelineManagerControl.FilterFinished
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelineManagerControl::FilterFinished


## -description


The <code>FilterFinished</code> method reports that a filter is finished processing.


## -parameters






#### - None


## -returns



<code>FilterFinished</code> returns an <b>HRESULT</b>.




## -remarks



The filter does not need to call the <code>FilterFinished</code> method. The filter pipeline assumes the filter has finished when the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554301">IPrintPipelineFilter::StartOperation</a> method returns. <code>FilterFinished</code> is provided for compatibility and, when called, it does nothing but returns.




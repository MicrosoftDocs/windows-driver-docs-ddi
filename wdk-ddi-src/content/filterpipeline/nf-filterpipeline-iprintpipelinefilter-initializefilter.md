---
UID: NF:filterpipeline.IPrintPipelineFilter.InitializeFilter
title: IPrintPipelineFilter::InitializeFilter
author: windows-driver-content
description: The InitializeFilter method initializes a filter.
old-location: print\iprintpipelinefilter_initializefilter.htm
old-project: print
ms.assetid: a28a8ee0-24df-45b5-8850-f3b3984b3b64
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: IPrintPipelineFilter interface [Print Devices],InitializeFilter method, IPrintPipelineFilter.InitializeFilter, IPrintPipelineFilter::InitializeFilter, InitializeFilter, InitializeFilter method [Print Devices], InitializeFilter method [Print Devices],IPrintPipelineFilter interface, filterpipeline/IPrintPipelineFilter::InitializeFilter, filterpipeline_cb281bce-8f53-4ade-91c1-2791baff0817.xml, print.iprintpipelinefilter_initializefilter
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
-	IPrintPipelineFilter.InitializeFilter
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelineFilter::InitializeFilter


## -description


The <code>InitializeFilter</code> method initializes a filter.


## -parameters




### -param pINegotiation




### -param pIPropertyBag [in]

A pointer to the<a href="https://msdn.microsoft.com/library/windows/hardware/ff554320">IPrintPipelinePropertyBag</a> interface.


### -param pIPipelineControl [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554303">IPrintPipelineManagerControl</a> interface.


#### - pICommunicator [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551050">IInterFilterCommunicator</a> interface.


## -returns



<code>InitializeFilter</code> returns an <b>HRESULT</b> value. The method should return a value other than "S_OK" or "S_FALSE" if the necessary operations are not performed inside <code>InitializeFilter</code>.




## -remarks



When the <code>InitializeFilter</code> method is called, the filters should:

<ul>
<li>
Get, add, or delete properties from the property bag.

</li>
<li>
Get the read and write interfaces.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551050">IInterFilterCommunicator</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554286">IPrintPipelineFilter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554303">IPrintPipelineManagerControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554320">IPrintPipelinePropertyBag</a>
 

 


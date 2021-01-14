---
UID: NF:filterpipeline.IPrintPipelineFilter.InitializeFilter
title: IPrintPipelineFilter::InitializeFilter (filterpipeline.h)
description: The InitializeFilter method initializes a filter.
old-location: print\iprintpipelinefilter_initializefilter.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["IPrintPipelineFilter::InitializeFilter"]
ms.keywords: IPrintPipelineFilter interface [Print Devices],InitializeFilter method, IPrintPipelineFilter.InitializeFilter, IPrintPipelineFilter::InitializeFilter, InitializeFilter, InitializeFilter method [Print Devices], InitializeFilter method [Print Devices],IPrintPipelineFilter interface, filterpipeline/IPrintPipelineFilter::InitializeFilter, filterpipeline_cb281bce-8f53-4ade-91c1-2791baff0817.xml, print.iprintpipelinefilter_initializefilter
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
 - IPrintPipelineFilter::InitializeFilter
 - filterpipeline/IPrintPipelineFilter::InitializeFilter
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - filterpipeline.h
api_name:
 - IPrintPipelineFilter::InitializeFilter
---

# IPrintPipelineFilter::InitializeFilter


## -description

The <code>InitializeFilter</code> method initializes a filter.

## -parameters

### -param pINegotiation

### -param pIPropertyBag 

[in]
A pointer to the<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag">IPrintPipelinePropertyBag</a> interface.

### -param pIPipelineControl 

[in]
A pointer to the <a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinemanagercontrol">IPrintPipelineManagerControl</a> interface.


#### - pICommunicator [in]

A pointer to the <a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator">IInterFilterCommunicator</a> interface.

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

<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator">IInterFilterCommunicator</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinefilter">IPrintPipelineFilter</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinemanagercontrol">IPrintPipelineManagerControl</a>



<a href="/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag">IPrintPipelinePropertyBag</a>


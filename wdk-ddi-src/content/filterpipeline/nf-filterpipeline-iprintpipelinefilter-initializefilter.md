---
UID: NF:filterpipeline.IPrintPipelineFilter.InitializeFilter
title: IPrintPipelineFilter::InitializeFilter (filterpipeline.h)
description: The InitializeFilter method initializes a filter.
tech.root: print
ms.date: 04/19/2022
keywords: ["IPrintPipelineFilter::InitializeFilter"]
ms.keywords: IPrintPipelineFilter interface [Print Devices],InitializeFilter method, IPrintPipelineFilter.InitializeFilter, IPrintPipelineFilter::InitializeFilter, InitializeFilter, InitializeFilter method [Print Devices], InitializeFilter method [Print Devices],IPrintPipelineFilter interface, filterpipeline/IPrintPipelineFilter::InitializeFilter, filterpipeline_cb281bce-8f53-4ade-91c1-2791baff0817.xml, print.iprintpipelinefilter_initializefilter
req.header: filterpipeline.h
req.include-header: Filterpipeline.h
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

## -description

The **InitializeFilter** method initializes a filter.

## -parameters

### -param pINegotiation [in]

A pointer to the [IInterFilterCommunicator](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator) interface.

### -param pIPropertyBag [in]

A pointer to the [IPrintPipelinePropertyBag](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag) interface.

### -param pIPipelineControl [in]

A pointer to the [IPrintPipelineManagerControl](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinemanagercontrol) interface.

## -returns

**InitializeFilter** returns an **HRESULT** value. The method should return a value other than **S_OK** or **S_FALSE** if the necessary operations are not performed inside **InitializeFilter**.

## -remarks

When the **InitializeFilter** method is called, the filters should:

- Get, add, or delete properties from the property bag.

- Get the read and write interfaces.

## -see-also

[IInterFilterCommunicator](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iinterfiltercommunicator)

[IPrintPipelineFilter](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinefilter)

[IPrintPipelineManagerControl](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinemanagercontrol)

[IPrintPipelinePropertyBag](/windows-hardware/drivers/ddi/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag)

---
UID: NF:filterpipeline.IPrintPipelinePropertyBag.AddProperty
title: IPrintPipelinePropertyBag::AddProperty (filterpipeline.h)
description: The AddProperty method adds a property to a property bag.
old-location: print\iprintpipelinepropertybag_addproperty.htm
tech.root: print
ms.assetid: ba994342-c203-443e-a9fd-60fd29721dae
ms.date: 04/20/2018
keywords: ["IPrintPipelinePropertyBag::AddProperty"]
ms.keywords: AddProperty, AddProperty method [Print Devices], AddProperty method [Print Devices],IPrintPipelinePropertyBag interface, IPrintPipelinePropertyBag interface [Print Devices],AddProperty method, IPrintPipelinePropertyBag.AddProperty, IPrintPipelinePropertyBag::AddProperty, filterpipeline/IPrintPipelinePropertyBag::AddProperty, filterpipeline_03ee8efb-3b2b-460a-9b95-e806dad5bb96.xml, print.iprintpipelinepropertybag_addproperty
f1_keywords:
 - "filterpipeline/IPrintPipelinePropertyBag.AddProperty"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- filterpipeline.h
api_name:
- IPrintPipelinePropertyBag.AddProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelinePropertyBag::AddProperty


## -description


The <code>AddProperty</code> method adds a property to a property bag.


## -parameters




### -param pszName [in]

The name of the property that you want to add to the property bag. You should uniquely identify this property so that it does not collide with others. For example, use a name like <i>MyCompanyName-MySetting</i>.


### -param pVar [in]

The <b>VARIANT</b> value to add to the property bag.


## -returns



<code>AddProperty</code> returns an <b>HRESULT</b> value.




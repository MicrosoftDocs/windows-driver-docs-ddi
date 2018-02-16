---
UID: NF:filterpipeline.IPrintPipelinePropertyBag.AddProperty
title: IPrintPipelinePropertyBag::AddProperty method
author: windows-driver-content
description: The AddProperty method adds a property to a property bag.
old-location: print\iprintpipelinepropertybag_addproperty.htm
old-project: print
ms.assetid: ba994342-c203-443e-a9fd-60fd29721dae
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: AddProperty, IPrintPipelinePropertyBag, IPrintPipelinePropertyBag::AddProperty, print.iprintpipelinepropertybag_addproperty, AddProperty method [Print Devices], IPrintPipelinePropertyBag interface, filterpipeline_03ee8efb-3b2b-460a-9b95-e806dad5bb96.xml, AddProperty method [Print Devices], filterpipeline/IPrintPipelinePropertyBag::AddProperty, IPrintPipelinePropertyBag interface [Print Devices], AddProperty method
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
-	filterpipeline.h
apiname:
-	IPrintPipelinePropertyBag.AddProperty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelinePropertyBag::AddProperty method


## -description


The <code>AddProperty</code> method adds a property to a property bag.


## -syntax


````
HRESULT AddProperty(
  [in] const wchar_t *pszName,
  [in] const VARIANT *pVar
);
````


## -parameters




### -param pszName [in]

The name of the property that you want to add to the property bag. You should uniquely identify this property so that it does not collide with others. For example, use a name like <i>MyCompanyName-MySetting</i>.


### -param pVar [in]

The <b>VARIANT</b> value to add to the property bag.


## -returns



<code>AddProperty</code> returns an <b>HRESULT</b> value.




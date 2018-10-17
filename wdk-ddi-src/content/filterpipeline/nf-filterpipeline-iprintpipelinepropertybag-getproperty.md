---
UID: NF:filterpipeline.IPrintPipelinePropertyBag.GetProperty
title: IPrintPipelinePropertyBag::GetProperty
author: windows-driver-content
description: The GetProperty method gets a property from a property bag.
old-location: print\iprintpipelinepropertybag_getproperty.htm
tech.root: print
ms.assetid: 10a5ada8-98ab-4e1c-a4b5-2f6d60674952
ms.date: 4/20/2018
ms.keywords: GetProperty, GetProperty method [Print Devices], GetProperty method [Print Devices],IPrintPipelinePropertyBag interface, IPrintPipelinePropertyBag interface [Print Devices],GetProperty method, IPrintPipelinePropertyBag.GetProperty, IPrintPipelinePropertyBag::GetProperty, filterpipeline/IPrintPipelinePropertyBag::GetProperty, filterpipeline_6a2e804b-b8dd-4e20-a71a-7817181b825c.xml, print.iprintpipelinepropertybag_getproperty
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
-	IPrintPipelinePropertyBag.GetProperty
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintPipelinePropertyBag::GetProperty


## -description


The <code>GetProperty</code> method gets a property from a property bag.


## -parameters




### -param pszName [in]

The name of the property that you want to get from the property bag.


### -param pVar [out]

The <b>VARIANT</b> value to get from the property bag.


## -returns



<code>GetProperty</code> returns an <b>HRESULT</b> value.




---
UID: NF:filterpipeline.IPrintPipelinePropertyBag.GetProperty
title: IPrintPipelinePropertyBag::GetProperty method
author: windows-driver-content
description: The GetProperty method gets a property from a property bag.
old-location: print\iprintpipelinepropertybag_getproperty.htm
old-project: print
ms.assetid: 10a5ada8-98ab-4e1c-a4b5-2f6d60674952
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: IPrintPipelinePropertyBag interface [Print Devices], GetProperty method, filterpipeline_6a2e804b-b8dd-4e20-a71a-7817181b825c.xml, GetProperty method [Print Devices], GetProperty method [Print Devices], IPrintPipelinePropertyBag interface, GetProperty, filterpipeline/IPrintPipelinePropertyBag::GetProperty, IPrintPipelinePropertyBag, IPrintPipelinePropertyBag::GetProperty, print.iprintpipelinepropertybag_getproperty
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
-	IPrintPipelinePropertyBag.GetProperty
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelinePropertyBag::GetProperty method


## -description


The <code>GetProperty</code> method gets a property from a property bag.


## -syntax


````
HRESULT GetProperty(
  [in]  const wchar_t *pszName,
  [out]       VARIANT *pVar
);
````


## -parameters




### -param pszName [in]

The name of the property that you want to get from the property bag.


### -param pVar [out]

The <b>VARIANT</b> value to get from the property bag.


## -returns


<code>GetProperty</code> returns an <b>HRESULT</b> value.



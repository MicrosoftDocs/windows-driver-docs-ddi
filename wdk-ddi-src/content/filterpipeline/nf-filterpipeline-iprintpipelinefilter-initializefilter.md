---
UID: NF:filterpipeline.IPrintPipelineFilter.InitializeFilter
title: IPrintPipelineFilter::InitializeFilter method
author: windows-driver-content
description: The InitializeFilter method initializes a filter.
old-location: print\iprintpipelinefilter_initializefilter.htm
old-project: print
ms.assetid: a28a8ee0-24df-45b5-8850-f3b3984b3b64
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintPipelineFilter, IPrintPipelineFilter interface [Print Devices], InitializeFilter method, IPrintPipelineFilter::InitializeFilter, InitializeFilter method [Print Devices], InitializeFilter method [Print Devices], IPrintPipelineFilter interface, InitializeFilter,IPrintPipelineFilter.InitializeFilter, filterpipeline/IPrintPipelineFilter::InitializeFilter, filterpipeline_cb281bce-8f53-4ade-91c1-2791baff0817.xml, print.iprintpipelinefilter_initializefilter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IPrintPipelineFilter.InitializeFilter
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# IPrintPipelineFilter::InitializeFilter method


## -description


The <code>InitializeFilter</code> method initializes a filter.


## -syntax


````
HRESULT InitializeFilter(
  [in] IInterFilterCommunicator     *pICommunicator,
  [in] IPrintPipelinePropertyBag    *pIPropertyBag,
  [in] IPrintPipelineManagerControl *pIPipelineControl
);
````


## -parameters




### -param pINegotiation




### -param pIPropertyBag [in]

A pointer to the<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinepropertybag.md">IPrintPipelinePropertyBag</a> interface.


### -param pIPipelineControl [in]

A pointer to the <a href="..\filterpipeline\nn-filterpipeline-iprintpipelinemanagercontrol.md">IPrintPipelineManagerControl</a> interface.


#### - pICommunicator [in]

A pointer to the <a href="..\filterpipeline\nn-filterpipeline-iinterfiltercommunicator.md">IInterFilterCommunicator</a> interface.


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

<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinepropertybag.md">IPrintPipelinePropertyBag</a>



<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinefilter.md">IPrintPipelineFilter</a>



<a href="..\filterpipeline\nn-filterpipeline-iprintpipelinemanagercontrol.md">IPrintPipelineManagerControl</a>



<a href="..\filterpipeline\nn-filterpipeline-iinterfiltercommunicator.md">IInterFilterCommunicator</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintPipelineFilter::InitializeFilter method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NF:filterpipeline.DrvPopulateFilterServices
title: DrvPopulateFilterServices function
author: windows-driver-content
description: The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter.
old-location: print\drvpopulatefilterservices.htm
tech.root: print
ms.assetid: A24DAC54-57FE-419D-8B5D-54B8AFC338DE
ms.date: 4/20/2018
ms.keywords: DrvPopulateFilterServices, DrvPopulateFilterServices function [Print Devices], filterpipeline/DrvPopulateFilterServices, print.drvpopulatefilterservices
ms.topic: function
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
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
-	HeaderDef
api_location:
-	Filterpipeline.h
api_name:
-	DrvPopulateFilterServices
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvPopulateFilterServices function


## -description


The <b>DrvPopulateFilterServices</b> function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate  filter service objects in the filter pipeline property bag specified by the <i>pPropertyBag</i> parameter.


## -parameters




### -param pPropertyBag [in]

Pointer to a print pipeline property bag.


## -returns



This function returns an HRESULT value.




## -remarks



The <a href="https://msdn.microsoft.com/7567c514-3034-4db0-9622-31d14eb3772e">XPSDrv printer driver</a> can specify filter service provider module using the &lt;<i>FilterServiceProvider</i>&gt;  or &lt;<i>OptionalFilterServiceProvider</i>&gt; element in the <a href="https://msdn.microsoft.com/586247bd-6d06-4728-a5f0-ee3fe1d09321">filter pipeline configuration file</a>.   The service provider module must export the <b>DrvPopulateFilterServices</b> function.




## -see-also




<a href="https://msdn.microsoft.com/586247bd-6d06-4728-a5f0-ee3fe1d09321">Filter pipeline configuration file</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554320">IPrintPipelinePropertyBag</a>



<a href="https://msdn.microsoft.com/7567c514-3034-4db0-9622-31d14eb3772e">XPSDrv printer driver</a>
 

 


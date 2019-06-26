---
UID: NF:filterpipeline.DrvPopulateFilterServices
title: DrvPopulateFilterServices function (filterpipeline.h)
description: The DrvPopulateFilterServices function is called by the XPSDrv filter pipeline manager to allow the service provider to instantiate filter service objects in the filter pipeline property bag specified by the pPropertyBag parameter.
old-location: print\drvpopulatefilterservices.htm
tech.root: print
ms.assetid: A24DAC54-57FE-419D-8B5D-54B8AFC338DE
ms.date: 04/20/2018
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Filterpipeline.h
api_name:
- DrvPopulateFilterServices
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



The <a href="https://docs.microsoft.com/windows-hardware/drivers/print/xpsdrv-printer-driver">XPSDrv printer driver</a> can specify filter service provider module using the <<i>FilterServiceProvider</i>>  or <<i>OptionalFilterServiceProvider</i>> element in the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/filter-pipeline-configuration-file">filter pipeline configuration file</a>.   The service provider module must export the <b>DrvPopulateFilterServices</b> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/print/filter-pipeline-configuration-file">Filter pipeline configuration file</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/filterpipeline/nn-filterpipeline-iprintpipelinepropertybag">IPrintPipelinePropertyBag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/print/xpsdrv-printer-driver">XPSDrv printer driver</a>
 

 


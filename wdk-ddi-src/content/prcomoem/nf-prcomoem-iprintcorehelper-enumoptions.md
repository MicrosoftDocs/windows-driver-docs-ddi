---
UID: NF:prcomoem.IPrintCoreHelper.EnumOptions
title: IPrintCoreHelper::EnumOptions (prcomoem.h)
description: The IPrintCoreHelper::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelper_enumoptions.htm
tech.root: print
ms.assetid: 2e46e8cd-b5e5-4116-b42c-b7adcee9d520
ms.date: 04/20/2018
keywords: ["IPrintCoreHelper::EnumOptions"]
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumOptions method, IPrintCoreHelper.EnumOptions, IPrintCoreHelper::EnumOptions, prcomoem/IPrintCoreHelper::EnumOptions, print.iprintcorehelper_enumoptions, print_unidrv-pscript_allplugins_2dc1f4f3-27ab-44d3-8778-45f2eafae92a.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelper.EnumOptions"
 - "IPrintCoreHelper.EnumOptions"
req.header: prcomoem.h
req.include-header: Prcomoem.h
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
- COM
api_location:
- Prcomoem.h
api_name:
- IPrintCoreHelper.EnumOptions
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper::EnumOptions


## -description


The <b>IPrintCoreHelper::EnumOptions</b> method gets a list of available options for the given feature. 


## -parameters




### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested. 


### -param pOptionList




### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


#### - pOptionList[] [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature that is specified in the <i>pszFeatureKeyword</i> parameter. <b>IPrintCoreHelper::EnumOptions</b> is responsible for allocating the memory for the array. The last element of the array must be a <b>NULL</b> string.


## -returns



<b>IPrintCoreHelper::EnumOptions</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



When <b>IPrintCoreHelper::EnumOptions</b> returns, the option list contains all options, regardless of constraints or other factors.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper">IPrintCoreHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-enumfeatures">IPrintCoreHelper::EnumFeatures</a>
 

 


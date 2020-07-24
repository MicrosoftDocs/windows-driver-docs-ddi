---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumOptions
title: IPrintCoreHelperUni::EnumOptions (prcomoem.h)
description: The IPrintCoreHelperUni::EnumOptions method gets a list of available options for the given feature.
old-location: print\iprintcorehelperuni_enumoptions.htm
tech.root: print
ms.assetid: 07ed6417-1cdc-4a56-88c3-c2171c54e77c
ms.date: 04/20/2018
keywords: ["IPrintCoreHelperUni::EnumOptions"]
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],EnumOptions method, IPrintCoreHelperUni.EnumOptions, IPrintCoreHelperUni::EnumOptions, prcomoem/IPrintCoreHelperUni::EnumOptions, print.iprintcorehelperuni_enumoptions, print_unidrv-pscript_allplugins_57929bdd-c8d4-4e48-be3d-449df47b744b.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelperUni.EnumOptions"
 - "IPrintCoreHelperUni.EnumOptions"
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
- IPrintCoreHelperUni.EnumOptions
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperUni::EnumOptions


## -description


The <code>IPrintCoreHelperUni::EnumOptions</code> method gets a list of available options for the given feature. 


## -parameters




### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested. 


### -param pOptionList




### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the <i>pOptionList</i> parameter.


#### - pOptionList[] [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature specified in the <i>pszFeatureKeyword</i> parameter. <code>IPrintCoreHelperUni::EnumOptions</code> is responsible for allocating the memory for the array. The last element of the array must be a <b>NULL</b> string.


## -returns



<code>IPrintCoreHelperUni::EnumOptions</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



When <code>IPrintCoreHelperUni::EnumOptions</code> returns, the option list contains all options, regardless of constraints or other factors.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni">IPrintCoreHelperUni</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-enumconstrainedoptions">IPrintCoreHelperUni::EnumConstrainedOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-enumfeatures">IPrintCoreHelperUni::EnumFeatures</a>
 

 


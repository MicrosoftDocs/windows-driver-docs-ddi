---
UID: NF:prcomoem.IPrintCoreHelper.EnumFeatures
title: IPrintCoreHelper::EnumFeatures (prcomoem.h)
description: The IPrintCoreHelper::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
old-location: print\iprintcorehelper_enumfeatures.htm
tech.root: print
ms.assetid: 21eddcfe-fe86-4135-a91c-42ec6e8e428a
ms.date: 04/20/2018
keywords: ["IPrintCoreHelper::EnumFeatures"]
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumFeatures method, IPrintCoreHelper.EnumFeatures, IPrintCoreHelper::EnumFeatures, prcomoem/IPrintCoreHelper::EnumFeatures, print.iprintcorehelper_enumfeatures, print_unidrv-pscript_allplugins_322210f8-379e-4b8a-973b-ed44a7245965.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelper.EnumFeatures"
 - "IPrintCoreHelper.EnumFeatures"
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
- IPrintCoreHelper.EnumFeatures
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper::EnumFeatures


## -description


The <b>IPrintCoreHelper::EnumFeatures</b> method gets a list of all available features, including synthesized and core driver-implement features.


## -parameters




### -param pFeatureList




### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the <i>pFeatureList</i> parameter.


#### - pFeatureList[] [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a <b>NULL</b> string. The array elements should be considered constants. The caller does not need to provide a buffer for the array, nor should the caller release the array.


## -returns



<b>IPrintCoreHelper::EnumFeatures</b> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.




## -remarks



For Unidrv features, the feature list is based on the GPD view of the configuration file, so features that are surrounded by *<b>Ifdef GDL_ENABLED</b>/*<b>Endif</b> directives are not visible and will not be reported by <b>IPrintCoreHelper::EnumFeatures</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper">IPrintCoreHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-enumoptions">IPrintCoreHelper::EnumOptions</a>
 

 


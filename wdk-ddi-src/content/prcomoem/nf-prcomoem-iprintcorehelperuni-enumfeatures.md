---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumFeatures
title: IPrintCoreHelperUni::EnumFeatures (prcomoem.h)
description: The IPrintCoreHelperUni::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperUni::EnumFeatures"]
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],EnumFeatures method, IPrintCoreHelperUni.EnumFeatures, IPrintCoreHelperUni::EnumFeatures, prcomoem/IPrintCoreHelperUni::EnumFeatures, print.iprintcorehelperuni_enumfeatures, print_unidrv-pscript_allplugins_a41557cd-962d-4b7c-960d-dd213b1a68e2.xml
req.header: prcomoem.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelperUni::EnumFeatures
 - prcomoem/IPrintCoreHelperUni::EnumFeatures
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperUni::EnumFeatures
---

## -description

The **IPrintCoreHelperUni::EnumFeatures** method gets a list of all available features, including synthesized and core driver-implement features.

## -parameters

### -param pFeatureList [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a **NULL** string.

### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the *pFeatureList* parameter.

## -returns

**IPrintCoreHelperUni::EnumFeatures** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

For Unidrv features, the feature list is based on the GPD view of the configuration file, so features that are surrounded by **Ifdef GDL_ENABLED / Endif** directives cannot be configured by using this method.

## -see-also

[IPrintCoreHelperUni](./nn-prcomoem-iprintcorehelperuni.md)

[IPrintCoreHelperUni::EnumOptions](./nf-prcomoem-iprintcorehelperuni-enumoptions.md)
---
UID: NF:prcomoem.IPrintCoreHelper.EnumFeatures
title: IPrintCoreHelper::EnumFeatures (prcomoem.h)
description: The IPrintCoreHelper::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelper::EnumFeatures"]
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumFeatures method, IPrintCoreHelper.EnumFeatures, IPrintCoreHelper::EnumFeatures, prcomoem/IPrintCoreHelper::EnumFeatures, print.iprintcorehelper_enumfeatures, print_unidrv-pscript_allplugins_322210f8-379e-4b8a-973b-ed44a7245965.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IPrintCoreHelper::EnumFeatures
 - prcomoem/IPrintCoreHelper::EnumFeatures
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelper::EnumFeatures
---

## -description

The **IPrintCoreHelper::EnumFeatures** method gets a list of all available features, including synthesized and core driver-implement features.

## -parameters

### -param pFeatureList [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a **NULL** string. The array elements should be considered constants. The caller does not need to provide a buffer for the array, nor should the caller release the array.

### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the *pFeatureList* parameter.

## -returns

**IPrintCoreHelper::EnumFeatures** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

For Unidrv features, the feature list is based on the GPD view of the configuration file, so features that are surrounded by **Ifdef GDL_ENABLED** / **Endif** directives are not visible and will not be reported by **IPrintCoreHelper::EnumFeatures**.

## -see-also

[IPrintCoreHelper](./nn-prcomoem-iprintcorehelper.md)

[IPrintCoreHelper::EnumOptions](./nf-prcomoem-iprintcorehelper-enumoptions.md)
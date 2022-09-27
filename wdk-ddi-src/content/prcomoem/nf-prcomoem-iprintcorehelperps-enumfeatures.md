---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumFeatures
title: IPrintCoreHelperPS::EnumFeatures (prcomoem.h)
description: The IPrintCoreHelperPS::EnumFeatures method gets a list of all available features, including synthesized and core driver-implement features.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperPS::EnumFeatures"]
ms.keywords: EnumFeatures, EnumFeatures method [Print Devices], EnumFeatures method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],EnumFeatures method, IPrintCoreHelperPS.EnumFeatures, IPrintCoreHelperPS::EnumFeatures, prcomoem/IPrintCoreHelperPS::EnumFeatures, print.iprintcorehelperps_enumfeatures, print_unidrv-pscript_allplugins_06a6f78b-fa5d-496e-b276-f32bba7c2502.xml
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
 - IPrintCoreHelperPS::EnumFeatures
 - prcomoem/IPrintCoreHelperPS::EnumFeatures
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperPS::EnumFeatures
---

## -description

The **IPrintCoreHelperPS::EnumFeatures** method gets a list of all available features, including synthesized and core driver-implement features.

## -parameters

### -param pFeatureList [out]

A pointer to an array of ANSI character strings that contain all of the features that are available for the current device. The final array element is indicated by a **NULL** string.

### -param pdwNumFeatures [out]

A pointer to a variable that receives the number of feature keywords in the array that is pointed to by the *pFeatureList* parameter.

## -returns

Returns **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -see-also

[IPrintCoreHelperPS](./nn-prcomoem-iprintcorehelperps.md)

[IPrintCoreHelperPS::EnumOptions](./nf-prcomoem-iprintcorehelperps-enumoptions.md)
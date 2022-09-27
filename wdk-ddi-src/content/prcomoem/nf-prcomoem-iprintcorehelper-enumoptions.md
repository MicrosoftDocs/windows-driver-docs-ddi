---
UID: NF:prcomoem.IPrintCoreHelper.EnumOptions
title: IPrintCoreHelper::EnumOptions (prcomoem.h)
description: The IPrintCoreHelper::EnumOptions method gets a list of available options for the given feature.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelper::EnumOptions"]
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumOptions method, IPrintCoreHelper.EnumOptions, IPrintCoreHelper::EnumOptions, prcomoem/IPrintCoreHelper::EnumOptions, print.iprintcorehelper_enumoptions, print_unidrv-pscript_allplugins_2dc1f4f3-27ab-44d3-8778-45f2eafae92a.xml
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
 - IPrintCoreHelper::EnumOptions
 - prcomoem/IPrintCoreHelper::EnumOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelper::EnumOptions
---

## -description

The **IPrintCoreHelper::EnumOptions** method gets a list of available options for the given feature.

## -parameters

### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested.

### -param pOptionList [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature that is specified in the *pszFeatureKeyword* parameter. **IPrintCoreHelper::EnumOptions** is responsible for allocating the memory for the array. The last element of the array must be a **NULL** string.

### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the *pOptionList* parameter.

## -returns

**IPrintCoreHelper::EnumOptions** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

When **IPrintCoreHelper::EnumOptions** returns, the option list contains all options, regardless of constraints or other factors.

## -see-also

[IPrintCoreHelper](./nn-prcomoem-iprintcorehelper.md)

[IPrintCoreHelper::EnumFeatures](./nf-prcomoem-iprintcorehelper-enumfeatures.md)
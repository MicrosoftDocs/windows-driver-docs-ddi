---
UID: NF:prcomoem.IPrintCoreHelperPS.EnumOptions
title: IPrintCoreHelperPS::EnumOptions (prcomoem.h)
description: The IPrintCoreHelperPS::EnumOptions method gets a list of available options for the given feature.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperPS::EnumOptions"]
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],EnumOptions method, IPrintCoreHelperPS.EnumOptions, IPrintCoreHelperPS::EnumOptions, prcomoem/IPrintCoreHelperPS::EnumOptions, print.iprintcorehelperps_enumoptions, print_unidrv-pscript_allplugins_89c5ea61-aedf-43c6-9a8b-020656476f35.xml
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
 - IPrintCoreHelperPS::EnumOptions
 - prcomoem/IPrintCoreHelperPS::EnumOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperPS::EnumOptions
---

## -description

The **IPrintCoreHelperPS::EnumOptions** method gets a list of available options for the given feature.

## -parameters

### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested.

### -param pOptionList [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature that is specified in the *pszFeatureKeyword* parameter. **IPrintCoreHelperPS::EnumOptions** is responsible for allocating the memory for the array. The last element of the array must be a **NULL** string.

### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the *pOptionList* parameter.

## -returns

**IPrintCoreHelperPS::EnumOptions** should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

When **IPrintCoreHelperPS::EnumOptions** returns, the option list contains all options, regardless of constraints or other factors.

## -see-also

[IPrintCoreHelperPS](./nn-prcomoem-iprintcorehelperps.md)

[IPrintCoreHelperPS::EnumConstrainedOptions](./nf-prcomoem-iprintcorehelperps-enumconstrainedoptions.md)

[IPrintCoreHelperPS::EnumFeatures](./nf-prcomoem-iprintcorehelperps-enumfeatures.md)
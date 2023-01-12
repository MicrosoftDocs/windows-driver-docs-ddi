---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumOptions
title: IPrintCoreHelperUni::EnumOptions (prcomoem.h)
description: The IPrintCoreHelperUni::EnumOptions method gets a list of available options for the given feature.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperUni::EnumOptions"]
ms.keywords: EnumOptions, EnumOptions method [Print Devices], EnumOptions method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],EnumOptions method, IPrintCoreHelperUni.EnumOptions, IPrintCoreHelperUni::EnumOptions, prcomoem/IPrintCoreHelperUni::EnumOptions, print.iprintcorehelperuni_enumoptions, print_unidrv-pscript_allplugins_57929bdd-c8d4-4e48-be3d-449df47b744b.xml
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
 - IPrintCoreHelperUni::EnumOptions
 - prcomoem/IPrintCoreHelperUni::EnumOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperUni::EnumOptions
---

## -description

The **IPrintCoreHelperUni::EnumOptions** method gets a list of available options for the given feature.

## -parameters

### -param pszFeatureKeyword [in]

An ANSI character string that contains the feature whose options are requested.

### -param pOptionList [out]

A pointer to an array of ANSI character strings that contain all of the options for the feature specified in the *pszFeatureKeyword* parameter. **IPrintCoreHelperUni::EnumOptions** is responsible for allocating the memory for the array. The last element of the array must be a **NULL** string.

### -param pdwNumOptions [out]

A pointer to a variable that receives the number of options in the option array that is pointed to by the *pOptionList* parameter.

## -returns

**IPrintCoreHelperUni::EnumOptions** should return **S_OK** if the operation succeeds. Otherwise, this method should return a standard COM error code.

## -remarks

When **IPrintCoreHelperUni::EnumOptions** returns, the option list contains all options, regardless of constraints or other factors.

## -see-also

[IPrintCoreHelperUni](./nn-prcomoem-iprintcorehelperuni.md)

[IPrintCoreHelperUni::EnumConstrainedOptions](./nf-prcomoem-iprintcorehelperuni-enumconstrainedoptions.md)

[IPrintCoreHelperUni::EnumFeatures](./nf-prcomoem-iprintcorehelperuni-enumfeatures.md)
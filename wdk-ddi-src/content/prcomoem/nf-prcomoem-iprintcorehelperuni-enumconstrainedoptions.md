---
UID: NF:prcomoem.IPrintCoreHelperUni.EnumConstrainedOptions
title: IPrintCoreHelperUni::EnumConstrainedOptions (prcomoem.h)
description: The IPrintCoreHelperUni::EnumConstrainedOptions method provides a list of all of the options that are constrained in a particular feature, based on current settings.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelperUni::EnumConstrainedOptions"]
ms.keywords: EnumConstrainedOptions, EnumConstrainedOptions method [Print Devices], EnumConstrainedOptions method [Print Devices],IPrintCoreHelperUni interface, IPrintCoreHelperUni interface [Print Devices],EnumConstrainedOptions method, IPrintCoreHelperUni.EnumConstrainedOptions, IPrintCoreHelperUni::EnumConstrainedOptions, prcomoem/IPrintCoreHelperUni::EnumConstrainedOptions, print.iprintcorehelperuni_enumconstrainedoptions, print_unidrv-pscript_allplugins_1acbff6a-b43d-4504-b2dc-69713a61261f.xml
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
 - IPrintCoreHelperUni::EnumConstrainedOptions
 - prcomoem/IPrintCoreHelperUni::EnumConstrainedOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelperUni::EnumConstrainedOptions
---

## -description

The **IPrintCoreHelperUni::EnumConstrainedOptions** method provides a list of all of the options that are constrained in a particular feature, based on current settings.

## -parameters

### -param pDevmode [in, optional]

A pointer to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. If this pointer is provided, **IPrintCoreHelperUni::EnumConstrainedOptions** should use the DEVMODEW structure that is pointed to by *pDevmode* instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from [IPrintOemUni::DevMode](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode), this parameter is required. In most other situations, the parameter should be **NULL**. When the core driver sets *pDevmode* to **NULL**, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets), is being serviced by the core driver's UI module.

### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the *pDevmode* parameter.

### -param pszFeatureKeyword [in]

A string of ANSI characters that contains the feature name.

### -param pConstrainedOptionList [out]

A pointer to an array of ANSI character strings. When **IPrintCoreHelperUni::EnumConstrainedOptions** returns, these strings will contain the names of all of the options that are constrained within the specified feature. The caller is not responsible for freeing the array or the individual strings in the array.

### -param pdwNumOptions [out]

A pointer to a variable that receives the number of constrained options in the array that is pointed to by the *pConstrainedOptionList* parameter.

## -returns

**IPrintCoreHelperUni::EnumConstrainedOptions** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The constrained options were set for the specified feature. |
| **E_FAIL** | The caller provided information that resulted in an invalid request, such as a request for a feature that does not exist. |
| **E_INVALIDARG** | One or more of the arguments were invalid. This value might mean that the feature is not supported. |
| **E_OUTOFMEMORY** | There was not enough memory to create the options array or the core driver could not service the request due to lack of memory. |
| **E_UNEXPECTED, or other failures not listed here** | An unexpected condition occurred. The core driver is probably in an invalid state. The caller should exit with a failure code. |

## -see-also

[IPrintCoreHelperUni](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperuni)

[IPrintCoreHelperUni::EnumOptions](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperuni-enumoptions)

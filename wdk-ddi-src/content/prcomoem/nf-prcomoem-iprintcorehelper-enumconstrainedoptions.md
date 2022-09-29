---
UID: NF:prcomoem.IPrintCoreHelper.EnumConstrainedOptions
title: IPrintCoreHelper::EnumConstrainedOptions (prcomoem.h)
description: The IPrintCoreHelper::EnumConstrainedOptions method provides a list of all of the options that are constrained in a particular feature, based on current settings.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelper::EnumConstrainedOptions"]
ms.keywords: EnumConstrainedOptions, EnumConstrainedOptions method [Print Devices], EnumConstrainedOptions method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],EnumConstrainedOptions method, IPrintCoreHelper.EnumConstrainedOptions, IPrintCoreHelper::EnumConstrainedOptions, prcomoem/IPrintCoreHelper::EnumConstrainedOptions, print.iprintcorehelper_enumconstrainedoptions, print_unidrv-pscript_allplugins_7a6e6657-1af2-4719-998a-a41090bee035.xml
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
 - IPrintCoreHelper::EnumConstrainedOptions
 - prcomoem/IPrintCoreHelper::EnumConstrainedOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelper::EnumConstrainedOptions
---

## -description

The **IPrintCoreHelper::EnumConstrainedOptions** method provides a list of all of the options that are constrained in a particular feature, based on current settings.

## -parameters

### -param pDevmode [in, optional]

A pointer to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. If this pointer is provided, **IPrintCoreHelper::EnumConstrainedOptions** should use the DEVMODEW structure that is pointed to by *pDevmode* instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from [IPrintOemPS::DevMode](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode) or [IPrintOemUni::DevMode](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode) or from a print ticket provider, this parameter is required. In most other situations, the parameter should be **NULL**. When the core driver sets *pDevmode* to **NULL**, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets), is being serviced by the core driver's UI module.

### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the *pDevmode* parameter.

### -param pszFeatureKeyword [in]

A string of ANSI characters that contain the feature name.

### -param pConstrainedOptionList [out]

A pointer to an array of ANSI character strings. When **IPrintCoreHelper::EnumConstrainedOptions** returns, these strings will contain the names of all of the options that are constrained within the specified feature. The caller is not responsible for freeing the array or the individual strings in the array.

### -param pdwNumOptions [out]

A pointer to a variable that receives the number of constrained options in the array that is pointed to by the *pConstrainedOptionList* parameter.

## -returns

**IPrintCoreHelper::EnumConstrainedOptions** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The constrained options were set for the specified feature. |
| **E_FAIL** | The caller provided information that resulted in an invalid request, such as a request for a feature that does not exist. |
| **E_INVALIDARG** | One or more of the arguments were invalid. This value might mean that the feature is not supported. |
| **E_OUTOFMEMORY** | There was not enough memory to create the options array or the core driver could not service the request because of lack of memory. |
| **E_UNEXPECTED, or other failures not explicitly listed here** | An unexpected condition occurred. The core driver is probably in an invalid state. The caller should exit with a failure code. |

## -see-also

[IPrintCoreHelper](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper)

[IPrintCoreHelper::EnumOptions](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-enumoptions)

[IPrintCoreHelper::WhyConstrained](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-whyconstrained)

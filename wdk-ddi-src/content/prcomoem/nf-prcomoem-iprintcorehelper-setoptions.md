---
UID: NF:prcomoem.IPrintCoreHelper.SetOptions
title: IPrintCoreHelper::SetOptions (prcomoem.h)
description: The IPrintCoreHelper::SetOptions method sets multiple feature-option pairs at the same time.
tech.root: print
ms.date: 07/25/2022
keywords: ["IPrintCoreHelper::SetOptions"]
ms.keywords: IPrintCoreHelper interface [Print Devices],SetOptions method, IPrintCoreHelper.SetOptions, IPrintCoreHelper::SetOptions, SetOptions, SetOptions method [Print Devices], SetOptions method [Print Devices],IPrintCoreHelper interface, prcomoem/IPrintCoreHelper::SetOptions, print.iprintcorehelper_setoptions, print_unidrv-pscript_allplugins_ad900ead-2d1f-41ab-9ee5-fc5e9f8130d7.xml
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
 - IPrintCoreHelper::SetOptions
 - prcomoem/IPrintCoreHelper::SetOptions
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Prcomoem.h
api_name:
 - IPrintCoreHelper::SetOptions
---

## -description

The **IPrintCoreHelper::SetOptions** method sets multiple feature-option pairs at the same time.

## -parameters

### -param pDevmode [in, optional]

A pointer to a [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure. If this pointer is provided, **IPrintCoreHelper::SetOptions** should use the DEVMODEW structure that is pointed to by *pDevmode* instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from either [IPrintOemPS::DevMode](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode) or [IPrintOemUni::DevMode](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode), this parameter is required. In most other situations, the parameter should be **NULL**. When the core driver sets *pDevmode* to **NULL**, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets), is being serviced by the core driver's UI module.

### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the *pDevmode* parameter.

### -param bResolveConflicts [in]

A Boolean value that indicates whether **IPrintCoreHelper::SetOptions** should resolve conflicts that arise from one or more constraints specified in the GPD or PPD view of the configuration file, as well as constraints for functionality implemented by Unidrv or Pscript or the print processor. If **TRUE**, this method should attempt to resolve the conflict. If **FALSE**, this method should not attempt to resolve conflicts. For more information, see the Remarks section.

### -param pFOPairs [in]

An array of [PRINT_FEATURE_OPTION](/windows-hardware/drivers/ddi/prcomoem/ns-prcomoem-_print_feature_option) elements, where each element contains a feature-option pair. Each feature-option pair lists a feature and the option to select for that feature. All settings are applied sequentially. Duplicates are not disallowed, but settings that appear later in the array (that is, at a higher index) override those that appear earlier in the array.

### -param cPairs [in]

The number of feature-option pairs that are pointed to by the *pFOPairs* parameter.

### -param pcPairsWritten [out]

A pointer to a variable that receives the number of feature-option pairs that were successfully saved before **IPrintCoreHelper::SetOptions** returned or failed. If this method returns successfully, **pcPairsWritten* will have the same value as *cPairs*. If the method fails,**pcPairsWritten* can have any value from zero through the value of *cPairs*. This parameter is optional and can be **NULL**.

### -param pdwResult [out]

A pointer to a variable that receives the status of the conflict resolution. The status can be one of the following values.

| Value | Description |
|--|--|
| SETOPTIONS_RESULT_NO_CONFLICT | No constraint that was specified in the GPD or PPD view of the configuration file was violated, relative to the new setting. |
| SETOPTIONS_RESULT_CONFLICT_RESOLVED | At least one constraint that was specified in the GPD or PPD view of the configuration file was violated, and the caller requested that the method should resolve conflicts. This value results in changed settings with conflicts resolved. |
| SETOPTIONS_RESULT_CONFLICT_NOT_RESOLVED | At least one constraint that was specified in the GPD or PPD view of the configuration file was violated, and the caller requested that the method should not resolve conflicts. The settings do not change, and conflicts remain. |

## -returns

**IPrintCoreHelper::SetOptions** should return one of the following values.

| Return code | Description |
|--|--|
| **S_OK** | The operation succeeded. |
| **E_INVALIDARG** | One or more of the arguments is invalid, or the feature was not supported. |
| **E_OUTOFMEMORY** | Memory for the result array could not be allocated. |

For other failures, the method should return a standard COM error code.

## -remarks

**IPrintCoreHelper::SetOptions** can be used to change multiple settings simultaneously and to resolve constraints after all of the selected options have been set. Changes to options are applied sequentially, starting from the beginning of the *pFOPairs* array, so if the same feature appears twice in this array, only the last option for the feature will be selected. Changes to options are not committed (that is, saved to the registry) unless the *bResolveConflicts* parameter is **TRUE**.

For most scenarios, the *bResolveConflicts* parameter should be set to **TRUE**. Set this parameter to **FALSE** if you want to prompt the user to resolve conflicts.

## -see-also

[IPrintCoreHelper](/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper)

[IPrintCoreHelper::GetOption](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-getoption)

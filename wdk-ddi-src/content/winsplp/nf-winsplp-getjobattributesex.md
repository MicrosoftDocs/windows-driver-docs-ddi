---
UID: NF:winsplp.GetJobAttributesEx
title: GetJobAttributesEx function (winsplp.h)
description: A print provider's GetJobAttributesEx function obtains information about a print job, including N-up and reverse printing options.
tech.root: print
ms.date: 11/30/2022
keywords: ["GetJobAttributesEx function"]
ms.keywords: GetJobAttributesEx, GetJobAttributesEx function [Print Devices], print.getjobattributesex, spoolfnc_45659d86-d97e-47c5-bbf7-49c990880b52.xml, winsplp/GetJobAttributesEx
req.header: winsplp.h
req.include-header: Winsplp.h
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - GetJobAttributesEx
 - winsplp/GetJobAttributesEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Spoolss.dll
api_name:
 - GetJobAttributesEx
---

## -description

> [!WARNING]
> Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

A print provider's **GetJobAttributesEx** function obtains information about a print job, including N-up and reverse printing options.

## -parameters

### -param pPrinterName [in]

Caller-supplied pointer to a NULL-terminated Unicode string that contains the printer name.

### -param pDevmode [in]

Caller-supplied pointer to a [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure that is passed to the print processor or printer driver.

### -param dwLevel [in]

Caller-supplied value that indicates the type of structure pointed to by *pAttributeInfo*, as indicated in the following table. For more information, see the **Remarks** section below.

| *dwLevel* value | Structure pointed to by *pAttributeInfo* |
|---|---|
| 1 | [ATTRIBUTE_INFO_1](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1) |
| 2 | [ATTRIBUTE_INFO_2](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2) |
| 3 | [ATTRIBUTE_INFO_3](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3) |
| 4 | [ATTRIBUTE_INFO_4](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4) |

### -param pAttributeInfo [out]

Caller-supplied pointer to an attribute information structure ([ATTRIBUTE_INFO_1](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_1), [ATTRIBUTE_INFO_2](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_2), [ATTRIBUTE_INFO_3](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3), or [ATTRIBUTE_INFO_4](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4)) that receives information about the print job.

### -param nSize [in]

Size of the buffer, in bytes, pointed to by *pAttributeInfo*.

### -param dwFlags [in]

If set by the caller to FILL_WITH_DEFAULTS, then the spooler will fill *pAttributeInfo* with default values from level 1 up to the level specified by *dwLevel*.

For example, if *dwLevel* is 4 and FILL_WITH_DEFAULTS is specified, *pAttributeInfo* will be filled with the following default member values of [ATTRIBUTE_INFO_4](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4):

**dwJobNumberOfPagesPerSide** = 1

**dwDrvNumberOfPagesPerSide** = 1

**dwNupBorderFlags** = 0

**dwJobPageOrderFlags** = 0

**dwDrvPageOrderFlags** = 0

**dwJobNumberOfCopies** = **dmCopies** member of [**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew)

**dwDrvNumberOfCopies** = **dmCopies** member of **DEVMODEW**

**dwColorOptimization** = 0

**dmPrintQuality** = **dmPrintQuality** member of **DEVMODEW**

**dmYResolution** = **dmYResolution** member of **DEVMODEW**

**dwNupDirection** = RIGHT_THEN_DOWN

**dwBookletFlags** = BOOKLET_EDGE_LEFT

**dwDuplexFlags** = 0

**dwScalingPercentX** = 100

**dwScalingPercentY** = 100

**dwJobHandlingFlags** = 0

## -returns

**GetJobAttributesEx** returns **TRUE** if it is successful in obtaining the print job attributes; otherwise, it returns **FALSE**.

## -remarks

This function first checks whether the driver supports the attribute level that is indicated by *dwLevel*. If the driver does not support that attribute level, then the function queries the driver for support for the next lower level, (*dwLevel* - 1), and continues to query for progressively lower levels of support until it obtains the level of support provided by the driver. If *dwFlags* is set to FILL_WITH_DEFAULTS, then the function fills in the default values for the unsupported levels.

## -see-also

[**ATTRIBUTE_INFO_3**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_3)

[**ATTRIBUTE_INFO_4**](/windows-hardware/drivers/ddi/winddiui/ns-winddiui-_attribute_info_4)

[**DEVMODEW**](/windows/win32/api/wingdi/ns-wingdi-devmodew)

[GetJobAttributes](/windows-hardware/drivers/ddi/winsplp/nf-winsplp-getjobattributes)

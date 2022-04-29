---
UID: NF:hidsdi.HidD_GetFeature
title: HidD_GetFeature function (hidsdi.h)
description: The HidD_GetFeature routine returns a feature report from a specified top-level collection.
old-location: hid\hidd_getfeature.htm
tech.root: hid
ms.date: 04/28/2022
keywords: ["HidD_GetFeature function"]
ms.keywords: HidD_GetFeature, HidD_GetFeature routine [Human Input Devices], hid.hidd_getfeature, hidfunc_2992bcaf-4ca6-4b6f-9a85-d0add8c7fe99.xml, hidsdi/HidD_GetFeature
req.header: hidsdi.h
req.include-header: Hidsdi.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
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
req.lib: Hid.lib
req.dll: Hid.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - HidD_GetFeature
 - hidsdi/HidD_GetFeature
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Hid.dll
api_name:
 - HidD_GetFeature
---

# HidD_GetFeature function

## -description

The **HidD_GetFeature** routine returns a feature report from a specified [top-level collection](/windows-hardware/drivers/hid/top-level-collections).

## -parameters

### -param HidDeviceObject [in]

An open handle to a top-level collection.

### -param ReportBuffer [out]

Pointer to a caller-allocated HID report buffer that the caller uses to specify a report ID. **HidD_GetFeature** uses *ReportBuffer* to return the specified feature report.

For more information about this parameter, see the [Remarks](#remarks) section.

### -param ReportBufferLength [in]

The size of the report buffer in bytes. The report buffer must be large enough to hold the feature report plus one additional byte that specifies a nonzero report ID. If report ID is not used, the ID value is zero.

## -returns

If **HidD_GetFeature** succeeds, it returns **TRUE**; otherwise, it returns **FALSE**. Use **[GetLastError](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)** to get extended error information.

## -remarks

Before it calls the **HidD_GetFeature** routine, the caller must do the following:

- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) includes report IDs, the caller must set the first byte of the *ReportBuffer* parameter to a nonzero report ID.
- If the [top-level collection](/windows-hardware/drivers/hid/top-level-collections) does not include report IDs, the caller must set the first byte of the *ReportBuffer* parameter to zero.

The feature report is returned in the *ReportBuffer*  parameter. Depending on the report ID, the caller parses the report by calling one of the following functions:

- [HidP_GetButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getbuttoncaps)
- [HidP_GetData](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getdata)
- [HidP_GetExtendedAttributes](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getextendedattributes)
- [HidP_GetScaledUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getscaledusagevalue)
- [HidP_GetSpecificButtonCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificbuttoncaps)
- [HidP_GetSpecificValueCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getspecificvaluecaps)
- [HidP_GetUsages](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusages)
- [HidP_GetUsagesEx](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagesex)
- [HidP_GetUsageValue](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevalue)
- [HidP_GetUsageValueArray](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getusagevaluearray)
- [HidP_GetValueCaps](/windows-hardware/drivers/ddi/hidpi/nf-hidpi-hidp_getvaluecaps)

For an example of how to parse a HID report, see the [HClient](/samples/browse/?redirectedfrom=MSDN-samples) sample application. This sample is located in the MSDN Code Gallery.

Only user-mode applications can call **HidD_GetFeature**. Kernel-mode drivers can use an [IOCTL_HID_GET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature) request.

## -see-also

- [Obtaining HID Reports](/windows-hardware/drivers/hid/obtaining-hid-reports)
- [Interpreting HID Reports](/windows-hardware/drivers/hid/interpreting-hid-reports)
- [HidD_GetInputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getinputreport)
- [HidD_SetFeature](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setfeature)
- [HidD_SetOutputReport](/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_setoutputreport)
- [IOCTL_HID_GET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_feature)
- [IOCTL_HID_GET_INPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_input_report)
- [IOCTL_HID_SET_FEATURE](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_feature)
- [IOCTL_HID_SET_OUTPUT_REPORT](/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_set_output_report)

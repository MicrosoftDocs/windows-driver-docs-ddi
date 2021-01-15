---
UID: NE:wdfdevice._WDF_SPECIAL_FILE_TYPE
title: _WDF_SPECIAL_FILE_TYPE (wdfdevice.h)
description: The WDF_SPECIAL_FILE_TYPE enumeration identifies special file types that a device can support.
old-location: wdf\wdf_special_file_type.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_SPECIAL_FILE_TYPE enumeration"]
ms.keywords: "*PWDF_SPECIAL_FILE_TYPE, DFDeviceObjectGeneralRef_66afb20c-b1d5-480a-b4bb-48b6e092fe5e.xml, PWDF_SPECIAL_FILE_TYPE, PWDF_SPECIAL_FILE_TYPE enumeration pointer, WDF_SPECIAL_FILE_TYPE, WDF_SPECIAL_FILE_TYPE enumeration, WdfSpecialFileBoot, WdfSpecialFileDump, WdfSpecialFileHibernation, WdfSpecialFileMax, WdfSpecialFilePaging, WdfSpecialFileUndefined, _WDF_SPECIAL_FILE_TYPE, kmdf.wdf_special_file_type, wdf.wdf_special_file_type, wdfdevice/PWDF_SPECIAL_FILE_TYPE, wdfdevice/WDF_SPECIAL_FILE_TYPE, wdfdevice/WdfSpecialFileBoot, wdfdevice/WdfSpecialFileDump, wdfdevice/WdfSpecialFileHibernation, wdfdevice/WdfSpecialFileMax, wdfdevice/WdfSpecialFilePaging, wdfdevice/WdfSpecialFileUndefined"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.typenames: WDF_SPECIAL_FILE_TYPE, *PWDF_SPECIAL_FILE_TYPE
f1_keywords:
 - _WDF_SPECIAL_FILE_TYPE
 - wdfdevice/_WDF_SPECIAL_FILE_TYPE
 - PWDF_SPECIAL_FILE_TYPE
 - wdfdevice/PWDF_SPECIAL_FILE_TYPE
 - WDF_SPECIAL_FILE_TYPE
 - wdfdevice/WDF_SPECIAL_FILE_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - _WDF_SPECIAL_FILE_TYPE
 - PWDF_SPECIAL_FILE_TYPE
 - WDF_SPECIAL_FILE_TYPE
---

# _WDF_SPECIAL_FILE_TYPE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_SPECIAL_FILE_TYPE</b> enumeration identifies special file types that a device can support.

## -enum-fields

### -field WdfSpecialFileUndefined

For internal use only.

### -field WdfSpecialFilePaging

The device supports paging files.

### -field WdfSpecialFileHibernation

The device supports hibernation files.

### -field WdfSpecialFileDump

The device supports dump files.

### -field WdfSpecialFileBoot

The device supports boot files. This constant is available in version 1.11 and later versions of KMDF.

### -field WdfSpecialFileMax

For internal use only.

## -remarks

For more information, see <a href="/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicesetspecialfilesupport">WdfDeviceSetSpecialFileSupport</a>


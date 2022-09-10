---
UID: NF:fltkernel.FltGetVolumeFromName
title: FltGetVolumeFromName function (fltkernel.h)
description: The FltGetVolumeFromName routine returns an opaque pointer for the volume whose name matches the value of the VolumeName parameter.
old-location: ifsk\fltgetvolumefromname.htm
tech.root: ifsk
ms.date: 08/10/2022
keywords: ["FltGetVolumeFromName function"]
ms.keywords: FltApiRef_e_to_o_1132de70-bc75-48a2-b0ae-d5b6d67a0a07.xml, FltGetVolumeFromName, FltGetVolumeFromName routine [Installable File System Drivers], fltkernel/FltGetVolumeFromName, ifsk.fltgetvolumefromname
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetVolumeFromName
 - fltkernel/FltGetVolumeFromName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetVolumeFromName
---

# FltGetVolumeFromName function

## -description

The **FltGetVolumeFromName** routine returns an opaque pointer for the volume whose name matches the value of the **VolumeName** parameter.

## -parameters

### -param Filter [in]

Opaque filter pointer for the caller. This parameter is required and cannot be **NULL**.

### -param VolumeName [in]

Pointer to a [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the volume name (for example, "\Device\HarddiskVolume1", "\DosDevices\D:", "\\??\D:", or "D:"). This parameter is required and cannot be **NULL**.

### -param RetVolume [out]

Pointer to a caller-allocated variable that receives an opaque pointer for the volume. This parameter is required and cannot be **NULL**.

## -returns

**FltGetVolumeFromName** returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_ACCESS_DENIED | The caller did not have FILE_READ_DATA access to the volume. This is an error code. |
| STATUS_FLT_DELETING_OBJECT | The volume is being torn down. This is an error code. |
| STATUS_INVALID_PARAMETER | An invalid value was specified for the **VolumeName** parameter. This is an error code. |
| STATUS_FLT_VOLUME_NOT_FOUND | No matching volume was found. This is an error code. |

## -remarks

**FltGetVolumeFromName** searches the Filter Manager's global list of volumes for a volume whose name matches **VolumeName**. The caller must have FILE_READ_DATA access to the volume. To locate the volume structure, **FltGetVolumeFromName** must first open the volume.

**FltGetVolumeFromName** adds a rundown reference to the opaque volume pointer returned in the **RetVolume** parameter. When this pointer is no longer needed, the caller must release it by calling [**FltObjectDereference**](nf-fltkernel-fltobjectdereference.md). Thus every successful call to **FltGetVolumeFromName** must be matched by a subsequent call to **FltObjectDereference**.

To get the volume name for a given volume, call [**FltGetVolumeName**](nf-fltkernel-fltgetvolumename.md).

To get the volume GUID name for a given volume, call [**FltGetVolumeGuidName**](nf-fltkernel-fltgetvolumeguidname.md).

## -see-also

[**FltGetFilterFromName**](nf-fltkernel-fltgetfilterfromname.md)

[**FltGetVolumeGuidName**](nf-fltkernel-fltgetvolumeguidname.md)

[**FltGetVolumeInstanceFromName**](nf-fltkernel-fltgetvolumeinstancefromname.md)

[**FltGetVolumeName**](nf-fltkernel-fltgetvolumename.md)

[**FltObjectDereference**](nf-fltkernel-fltobjectdereference.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

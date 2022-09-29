---
UID: NF:fltkernel.FltGetVolumeName
title: FltGetVolumeName function (fltkernel.h)
description: The FltGetVolumeName routine gets the volume name for a given volume.
old-location: ifsk\fltgetvolumename.htm
tech.root: ifsk
ms.date: 08/10/2022
keywords: ["FltGetVolumeName function"]
ms.keywords: FltApiRef_e_to_o_8d8cee36-2d14-4d5e-b95a-065a50d83f15.xml, FltGetVolumeName, FltGetVolumeName routine [Installable File System Drivers], fltkernel/FltGetVolumeName, ifsk.fltgetvolumename
req.header: fltkernel.h
req.include-header: FltKernel.h
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetVolumeName
 - fltkernel/FltGetVolumeName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetVolumeName
---

# FltGetVolumeName function

## -description

The **FltGetVolumeName** routine gets the volume name for a given volume.

## -parameters

### -param Volume [in]

Opaque pointer for the volume. This parameter is required and cannot be **NULL**.

### -param VolumeName [in, out, optional]

Pointer to a caller-allocated [**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure that contains the volume's non-persistent device object name (for example, "\Device\HarddiskVolume1") when STATUS_SUCCESS is returned. Be aware that pool for **VolumeName->Buffer** is also caller-allocated.

This parameter is optional and can be **NULL**; however it must be non-**NULL** if **BufferSizeNeeded** is **NULL**. If this parameter is **NULL** and **BufferSizeNeeded** is not **NULL**, **FltGetVolumeName** stores the buffer size needed for the requested volume name in the **BufferSizeNeeded** parameter and returns STATUS_BUFFER_TOO_SMALL. See Remarks.

### -param BufferSizeNeeded [out, optional]

Pointer to a caller-allocated variable that receives the size, in bytes, of the requested volume name. This parameter is optional and can be **NULL**; however, it must be non-**NULL** if **VolumeName** is **NULL** so that **FltGetVolumeName** can store the buffer size needed for the requested volume name.

## -returns

**FltGetVolumeName** returns one of the following NTSTATUS values:

| Return code | Description |
| ----------- | ----------- |
| STATUS_SUCCESS | The UNICODE_STRING structure, pointed to by **VolumeName**, contains the name of the volume in the **Buffer** member for the structure and the length of the name, in bytes, in the **Length** member. |
| STATUS_BUFFER_TOO_SMALL | The **Buffer** member of the UNICODE_STRING structure, pointed to by **VolumeName**, is too small (as indicated by its **MaximumLength** member) to contain the entire volume name. This is an error code. |
| STATUS_INVALID_PARAMETER | **VolumeName** and **BufferSizeNeeded** are both **NULL**. This is an error code. |

## -remarks

For this routine to succeed, the **Buffer** member of the UNICODE_STRING structure (pointed to by **VolumeName**) must be large enough, as indicated by its **MaximumLength** member, to contain the entire volume name string.

The following pseudocode shows one possible method to successfully acquire a volume name if **BufferSizeNeeded** is unknown:

* Call **FltGetVolumeName** to determine the required pool for **Buffer** and the required size for **MaximumLength**. For example: ```FltGetVolumeName(VolumePtr, NULL, &VolumeNameSize);```

* Allocate ```VolumeNameSize``` bytes of pool for **Buffer** and set **MaximumLength** to ```VolumeNameSize```.

* Call **FltGetVolumeName** again to acquire the volume name. For example: ```FltGetVolumeName(VolumePtr, &VolumeNameStruct, NULL);```

```VolumeNameStruct.Buffer``` contains the Unicode volume name string, which is ```VolumeNameStruct.Length``` bytes in length.

To get the volume GUID name for a given volume, call [**FltGetVolumeGuidName**](nf-fltkernel-fltgetvolumeguidname.md).

To get an opaque volume pointer for a volume with a given name, call [**FltGetVolumeFromName**](nf-fltkernel-fltgetvolumefromname.md).

For more information about how to name a volume, see [Supporting Mount Manager Requests in a Storage Class Driver**](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**FilterGetDosName**](/windows/win32/api/fltuser/nf-fltuser-filtergetdosname)

[**FltGetVolumeFromName**](nf-fltkernel-fltgetvolumefromname.md)

[**FltGetVolumeGuidName**](nf-fltkernel-fltgetvolumeguidname.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

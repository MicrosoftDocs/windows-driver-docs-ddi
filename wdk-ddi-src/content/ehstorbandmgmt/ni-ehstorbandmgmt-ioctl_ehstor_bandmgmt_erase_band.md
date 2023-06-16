---
UID: NI:ehstorbandmgmt.IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
title: IOCTL_EHSTOR_BANDMGMT_ERASE_BAND (ehstorbandmgmt.h)
description: The IOCTL_EHSTOR_BANDMGMT_ERASE_BAND request will cryptographically erase and reset the authentication key of a band. The remaining configuration of the band is left unmodified.
old-location: storage\ioctl_ehstor_bandmgmt_erase_band.htm
tech.root: storage
ms.date: 05/24/2022
keywords: ["IOCTL_EHSTOR_BANDMGMT_ERASE_BAND IOCTL"]
ms.keywords: IOCTL_EHSTOR_BANDMGMT_ERASE_BAND, IOCTL_EHSTOR_BANDMGMT_ERASE_BAND control, IOCTL_EHSTOR_BANDMGMT_ERASE_BAND control code [Storage Devices], ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ERASE_BAND, storage.ioctl_ehstor_bandmgmt_erase_band
req.header: ehstorbandmgmt.h
req.include-header: EhStorBandMgmt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
 - IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
 - ehstorbandmgmt/IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorBandMgmt.h
api_name:
 - IOCTL_EHSTOR_BANDMGMT_ERASE_BAND
---

# IOCTL_EHSTOR_BANDMGMT_ERASE_BAND IOCTL

## -description

The **IOCTL_EHSTOR_BANDMGMT_ERASE_BAND** request cryptographically erases and resets the authentication key of a band. The remaining configuration of the band is left unmodified.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The input buffer at **Irp->AssociatedIrp.SystemBuffer** must contain an [**ERASE_BAND_PARAMETERS**](ns-ehstorbandmgmt-_erase_band_parameters.md) and possibly an **AUTH_KEY** structure.

If the **NewAuthKeyOffset** member of [**ERASE_BAND_PARAMETERS**](ns-ehstorbandmgmt-_erase_band_parameters.md) is set to **EHSTOR_BANDMGR_NO_KEY**, the input data in the system buffer need not include an **AUTH_KEY** structure.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** indicates the size, in bytes, of the buffer, which must be at least ```sizeof(ERASE_BAND_PARAMETERS) + sizeof(AUTH_KEY)```.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

None.

### -inout-buffer-length

None.

### -status-block

One of the following values can be returned in the **Status** field.

| Status Value | Description |
| ------------ | ----------- |
| STATUS_SUCCESS                | The band was successfully erased. |
| STATUS_INVALID_DEVICE_REQUEST | The storage device does not support band management. |
| STATUS_INVALID_BUFFER_SIZE    | The input buffer size is incorrect. |
| STATUS_INVALID_PARAMETER      | Information in the input buffer is invalid. |
| STATUS_ACCESS_DENIED          | The erase authentication key is not a default key and the band cannot be erased. |
| STATUS_NOT_FOUND              | The band was not found for the selection criteria provided. |
| STATUS_IO_DEVICE_ERROR        | Communication failed. The storage device might be incompatible with security protocols. |

## -remarks

A current erase authentication key is not provided in an **IOCTL_EHSTOR_BANDMGMT_ERASE_BAND** request. The erase authentication key for the storage device is previously configured.

No method is provided in Windows to change the erase authentication key for a storage device. Provided that the correct parameters are given as input in the system buffer, this request should succeed. If  the erase authentication key was changed outside of Windows, such as in a dual-boot environment with a different operating system, this request may fail.

When a band is erased with **IOCTL_EHSTOR_BANDMGMT_ERASE_BAND**, the only prior properties that remain are band start and band size. The previous media encryption key is removed and a new key is generated. Locking is set to **PERSISTANT_UNLOCK** for both reading and writing. Security metadata previously set is erased. The new authentication key specified in  [**ERASE_BAND_PARAMETERS**](ns-ehstorbandmgmt-_erase_band_parameters.md) is set unless use  of the default key is indicated.

To prevent other applications from taking control of a band and erase by using the default key, a new authentication key should be included with the **IOCTL_EHSTOR_BANDMGMT_ERASE_BAND** request.

The changes made to the band table by this request are committed to the device atomically before the IOCTL request completes. Therefore, it is guaranteed that the band is modified with all of its properties set or no properties set at all should a system or power failure occur.

## -see-also

[**ERASE_BAND_PARAMETERS**](ns-ehstorbandmgmt-_erase_band_parameters.md)

[**IOCTL_EHSTOR_BANDMGMT_DELETE_BAND**](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_delete_band.md)

[**IOCTL_EHSTOR_BANDMGMT_ERASE_ALL_BANDS**](ni-ehstorbandmgmt-ioctl_ehstor_bandmgmt_erase_all_bands.md)

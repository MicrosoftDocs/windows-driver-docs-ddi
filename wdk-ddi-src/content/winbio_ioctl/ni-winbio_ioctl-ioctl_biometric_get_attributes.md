---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_GET_ATTRIBUTES
title: IOCTL_BIOMETRIC_GET_ATTRIBUTES (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.
old-location: biometric\ioctl_biometric_get_attributes.htm
tech.root: biometric
ms.assetid: 7a855435-017e-4724-adb4-976403015a93
ms.date: 02/20/2018
keywords: ["IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL"]
ms.keywords: IOCTL_BIOMETRIC_GET_ATTRIBUTES, IOCTL_BIOMETRIC_GET_ATTRIBUTES control, IOCTL_BIOMETRIC_GET_ATTRIBUTES control code [Biometric Devices], biometric.ioctl_biometric_get_attributes, biometric_ref_ee60223e-6d9a-4533-9449-b7a7463f835e.xml, winbio_ioctl/IOCTL_BIOMETRIC_GET_ATTRIBUTES
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
 - IOCTL_BIOMETRIC_GET_ATTRIBUTES
 - winbio_ioctl/IOCTL_BIOMETRIC_GET_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winbio_ioctl.h
api_name:
 - IOCTL_BIOMETRIC_GET_ATTRIBUTES
---

# IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL


## -description

The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.

## -ioctlparameters

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_sensor_attributes">WINBIO_SENSOR_ATTRIBUTES</a> structure.

### -output-buffer-length

The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.

### -in-out-buffer

### -inout-buffer-length

### -status-block

Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

|Status value|Description|
|--- |--- |
|S_OK, STATUS_SUCCESS|The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.|
|E_INVALIDARG|The parameters were not specified correctly.|
|E_UNKNOWN|Any other failure that prevents the payload from being filled in.|
|E_UNEXPECTED|Any other failure that prevents the payload from being filled in.|
|E_FAIL|Any other failure that prevents the payload from being filled in.|

## -remarks

If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of <a href="/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_sensor_attributes">WINBIO_SENSOR_ATTRIBUTES</a> with an HRESULT value indicating the status of the biometric operation.
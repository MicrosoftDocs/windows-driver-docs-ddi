---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_GET_SENSOR_STATUS
title: IOCTL_BIOMETRIC_GET_SENSOR_STATUS
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL tells the driver to perform any necessary steps to collect the current operating status of the device. Vendor-supplied WBDI drivers must support this IOCTL.
old-location: biometric\ioctl_biometric_get_sensor_status.htm
old-project: biometric
ms.assetid: 88a2a73b-4fce-4f7a-b73b-ab66e136320d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IWiaTransferCallback, IWiaTransferCallback::TransferCallback, TransferCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BIOMETRIC_GET_SENSOR_STATUS
req.alt-loc: Winbio_ioctl.h
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
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL



## -description
The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL tells the driver to perform any necessary steps to collect the current operating status of the device. Vendor-supplied WBDI drivers must support this IOCTL.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_diagnostics.md">WINBIO_DIAGNOSTICS</a> structure.


### -output-buffer-length
The length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_diagnostics.md">WINBIO_DIAGNOSTICS</a> structure.

The vendor-supplied driver can optionally return a DWORD-sized buffer that specifies the buffer size necessary for the requested operation.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

S_OK, STATUS_SUCCESS

The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.

E_INVALIDARG

The parameters were not specified correctly.

E_UNKNOWN

Any other failure that prevents the payload from being filled in.

E_UNEXPECTED

Any other failure that prevents the payload from being filled in.

E_FAIL

Any other failure that prevents the payload from being filled in.

 


## -remarks
If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of WINBIO_DIAGNOSTICS with the status of the Biometric operation. </p>
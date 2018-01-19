---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_SET_INDICATOR
title: IOCTL_BIOMETRIC_SET_INDICATOR
author: windows-driver-content
description: The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.
old-location: biometric\ioctl_biometric_set_indicator.htm
old-project: biometric
ms.assetid: 5aaaf178-a137-4a98-a77f-b426514a8cd9
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
req.alt-api: IOCTL_BIOMETRIC_SET_INDICATOR
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

# IOCTL_BIOMETRIC_SET_INDICATOR IOCTL



## -description
The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.  The light can be turned on or off.  This IOCTL is optional.This IOCTL must be implemented if the driver supports the WINBIO_CAPABILITY_INDICATOR capability. 



This IOCTL must be implemented if the driver supports the WINBIO_CAPABILITY_INDICATOR capability. 



## -ioctlparameters

### -input-buffer

<a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_set_indicator.md">WINBIO_SET_INDICATOR</a>



### -input-buffer-length
Length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_set_indicator.md">WINBIO_SET_INDICATOR</a> structure.


### -output-buffer
The AssociatedIrp.SystemBuffer member points to a buffer that contains a WINBIO_BLANK_PAYLOAD structure.


### -output-buffer-length
The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.


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
If the vendor-supplied driver passes back the entire payload, it should fill in the WinBioHresult member of WINBIO_BLANK_PAYLOAD with the status of the biometric operation.

Possible values include:



The operation completed successfully.

The diagnostics did not complete due to device error.</p>
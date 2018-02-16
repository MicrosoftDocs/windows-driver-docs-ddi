---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_GET_ATTRIBUTES
title: IOCTL_BIOMETRIC_GET_ATTRIBUTES
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.
old-location: biometric\ioctl_biometric_get_attributes.htm
old-project: biometric
ms.assetid: 7a855435-017e-4724-adb4-976403015a93
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: biometric.ioctl_biometric_get_attributes, IOCTL_BIOMETRIC_GET_ATTRIBUTES control code [Biometric Devices], IOCTL_BIOMETRIC_GET_ATTRIBUTES, winbio_ioctl/IOCTL_BIOMETRIC_GET_ATTRIBUTES, biometric_ref_ee60223e-6d9a-4533-9449-b7a7463f835e.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winbio_ioctl.h
apiname:
-	IOCTL_BIOMETRIC_GET_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product: Windows 10 or later.
---

# IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_sensor_attributes.md">WINBIO_SENSOR_ATTRIBUTES</a> structure.


### -output-buffer-length

The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
S_OK, STATUS_SUCCESS

</td>
<td>
The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.

</td>
</tr>
<tr>
<td>
E_INVALIDARG

</td>
<td>
The parameters were not specified correctly.

</td>
</tr>
<tr>
<td>
E_UNKNOWN

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
<tr>
<td>
E_UNEXPECTED

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
<tr>
<td>
E_FAIL

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
</table>
 


## -remarks



If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_sensor_attributes.md">WINBIO_SENSOR_ATTRIBUTES</a> with an HRESULT value indicating the status of the biometric operation.




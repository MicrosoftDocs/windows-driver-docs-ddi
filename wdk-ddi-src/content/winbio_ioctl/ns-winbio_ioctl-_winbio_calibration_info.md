---
UID: NS:winbio_ioctl._WINBIO_CALIBRATION_INFO
title: "_WINBIO_CALIBRATION_INFO"
author: windows-driver-content
description: The IOCTL_BIOMETRIC_CALIBRATE IOCTL returns the WINBIO_CALIBRATION_INFO structure as output.
old-location: biometric\winbio_calibration_info.htm
old-project: biometric
ms.assetid: 12ea0460-30c1-4ce0-9a3b-c59a71493fe7
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWINBIO_CALIBRATION_INFO, PWINBIO_CALIBRATION_INFO, PWINBIO_CALIBRATION_INFO structure pointer [Biometric Devices], WINBIO_CALIBRATION_INFO, WINBIO_CALIBRATION_INFO structure [Biometric Devices], _WINBIO_CALIBRATION_INFO, biometric.winbio_calibration_info, biometric_ref_15065b26-3c1d-49f5-8546-b8962f848072.xml, winbio_ioctl/PWINBIO_CALIBRATION_INFO, winbio_ioctl/WINBIO_CALIBRATION_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	winbio_ioctl.h
apiname:
-	WINBIO_CALIBRATION_INFO
product: Windows
targetos: Windows
req.typenames: WINBIO_CALIBRATION_INFO, *PWINBIO_CALIBRATION_INFO
req.product: Windows 10 or later.
---

# _WINBIO_CALIBRATION_INFO structure


## -description


The <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_calibrate.md">IOCTL_BIOMETRIC_CALIBRATE</a> IOCTL returns the WINBIO_CALIBRATION_INFO structure as output.


## -syntax


````
typedef struct _WINBIO_CALIBRATION_INFO {
  DWORD       PayloadSize;
  HRESULT     WinBioHresult;
  WINBIO_DATA CalibrationData;
} WINBIO_CALIBRATION_INFO, *PWINBIO_CALIBRATION_INFO;
````


## -struct-fields




### -field PayloadSize

The total size of the payload.  This includes the fixed length structure and any variable data at the end.


### -field WinBioHresult

The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values for this member.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
S_OK

</td>
<td>
The operation completed successfully.

</td>
</tr>
<tr>
<td>
HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)

</td>
<td>
The driver could not gather the necessary information from the device.

</td>
</tr>
<tr>
<td>
WINBIO_E_DEVICE_BUSY

</td>
<td>
The device is in the middle of a vendor-specific operation.  This should only be returned when the device cannot be reset, and the vendor-specific operation cannot be canceled.

</td>
</tr>
</table>
 


### -field CalibrationData

A structure of type <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_data.md">WINBIO_DATA</a> that contains calibration data specific to this sensor.  This member is optional.


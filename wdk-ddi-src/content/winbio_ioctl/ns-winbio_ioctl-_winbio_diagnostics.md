---
UID: NS:winbio_ioctl._WINBIO_DIAGNOSTICS
title: _WINBIO_DIAGNOSTICS (winbio_ioctl.h)
description: The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL returns the WINBIO_DIAGNOSTICS structure as output.
old-location: biometric\winbio_diagnostics.htm
tech.root: biometric
ms.assetid: 06f6abf1-9b44-4cf3-96d3-2017e0f6adda
ms.date: 02/20/2018
keywords: ["_WINBIO_DIAGNOSTICS structure"]
ms.keywords: "*PWINBIO_DIAGNOSTICS, PWINBIO_DIAGNOSTICS, PWINBIO_DIAGNOSTICS structure pointer [Biometric Devices], WINBIO_DIAGNOSTICS, WINBIO_DIAGNOSTICS structure [Biometric Devices], _WINBIO_DIAGNOSTICS, biometric.winbio_diagnostics, biometric_ref_eca83e57-bec6-4d83-8596-978b73eed6de.xml, winbio_ioctl/PWINBIO_DIAGNOSTICS, winbio_ioctl/WINBIO_DIAGNOSTICS"
f1_keywords:
 - "winbio_ioctl/WINBIO_DIAGNOSTICS"
 - "WINBIO_DIAGNOSTICS"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winbio_ioctl.h
api_name:
- WINBIO_DIAGNOSTICS
product:
- Windows
targetos: Windows
req.typenames: WINBIO_DIAGNOSTICS, *PWINBIO_DIAGNOSTICS
---

# _WINBIO_DIAGNOSTICS structure


## -description


The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_get_sensor_status">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a> IOCTL returns the WINBIO_DIAGNOSTICS structure as output.


## -struct-fields

### -field PayloadSize

The total size of the payload.  This includes the fixed length structure and any variable data at the end.

### -field WinBioHresult

The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values.

|Status value|Description|
|--- |--- |
|S_OK|The operation completed successfully.|
|HRESULT_FROM_NT(STATUS_IO_DEVICE_ERROR)|The driver could not gather the necessary information from the device.|

### -field SensorStatus

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_capture_data">WINBIO_SENSOR_STATUS</a> that contains the operating status of the biometric sensor.

### -field VendorDiagnostics

An optional <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ns-winbio_ioctl-_winbio_data">WINBIO_DATA</a> structure for vendor-specific additional information.

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winbio_ioctl/ni-winbio_ioctl-ioctl_biometric_get_sensor_status">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a>
 

 


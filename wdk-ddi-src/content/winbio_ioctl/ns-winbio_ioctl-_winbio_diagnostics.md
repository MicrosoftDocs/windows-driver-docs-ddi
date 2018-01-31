---
UID: NS:winbio_ioctl._WINBIO_DIAGNOSTICS
title: "_WINBIO_DIAGNOSTICS"
author: windows-driver-content
description: The IOCTL_BIOMETRIC_GET_SENSOR_STATUS IOCTL returns the WINBIO_DIAGNOSTICS structure as output.
old-location: biometric\winbio_diagnostics.htm
old-project: biometric
ms.assetid: 06f6abf1-9b44-4cf3-96d3-2017e0f6adda
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: WINBIO_DIAGNOSTICS, *PWINBIO_DIAGNOSTICS, PWINBIO_DIAGNOSTICS structure pointer [Biometric Devices], _WINBIO_DIAGNOSTICS, PWINBIO_DIAGNOSTICS, biometric_ref_eca83e57-bec6-4d83-8596-978b73eed6de.xml, winbio_ioctl/WINBIO_DIAGNOSTICS, biometric.winbio_diagnostics, winbio_ioctl/PWINBIO_DIAGNOSTICS, WINBIO_DIAGNOSTICS structure [Biometric Devices]
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
-	WINBIO_DIAGNOSTICS
product: Windows
targetos: Windows
req.typenames: "*PWINBIO_DIAGNOSTICS, WINBIO_DIAGNOSTICS"
req.product: Windows 10 or later.
---

# _WINBIO_DIAGNOSTICS structure


## -description


The <a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_sensor_status.md">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a> IOCTL returns the WINBIO_DIAGNOSTICS structure as output.


## -syntax


````
typedef struct _WINBIO_DIAGNOSTICS {
  DWORD                PayloadSize;
  HRESULT              WinBioHresult;
  WINBIO_SENSOR_STATUS SensorStatus;
  WINBIO_DATA          VendorDiagnostics;
} WINBIO_DIAGNOSTICS, *PWINBIO_DIAGNOSTICS;
````


## -struct-fields




#### - PayloadSize

The total size of the payload.  This includes the fixed length structure and any variable data at the end.


#### - WinBioHresult

The status detail of the I/O operation.  This is where WINBIO error and information codes will be passed. The following table shows possible values.
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
</table> 


#### - SensorStatus

A structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff536476">WINBIO_SENSOR_STATUS</a> that contains the operating status of the biometric sensor.


#### - VendorDiagnostics

An optional <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_data.md">WINBIO_DATA</a> structure for vendor-specific additional information.


## -see-also

<a href="..\winbio_ioctl\ni-winbio_ioctl-ioctl_biometric_get_sensor_status.md">IOCTL_BIOMETRIC_GET_SENSOR_STATUS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [biometric\biometric]:%20WINBIO_DIAGNOSTICS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


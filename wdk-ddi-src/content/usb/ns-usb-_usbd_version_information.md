---
UID: NS:usb._USBD_VERSION_INFORMATION
title: _USBD_VERSION_INFORMATION (usb.h)
description: The USBD_VERSION_INFORMATION structure is used by the GetUSBDIVersion function to report its output data.
old-location: buses\usbd_version_information.htm
tech.root: usbref
ms.assetid: 37dc1e94-18cb-48d5-81a2-74d03cef4d5d
ms.date: 05/07/2018
ms.keywords: "*PUSBD_VERSION_INFORMATION, PUSBD_VERSION_INFORMATION, PUSBD_VERSION_INFORMATION structure pointer [Buses], USBD_VERSION_INFORMATION, USBD_VERSION_INFORMATION structure [Buses], _USBD_VERSION_INFORMATION, buses.usbd_version_information, usb/PUSBD_VERSION_INFORMATION, usb/USBD_VERSION_INFORMATION, usbstrct_2871bd56-3ee1-48ab-8353-d19b74470ff1.xml"
ms.topic: struct
req.header: usb.h
req.include-header: Usbbusif.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usb.h
api_name:
- USBD_VERSION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
---

# _USBD_VERSION_INFORMATION structure


## -description


The <b>USBD_VERSION_INFORMATION</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/nc-usbbusif-pusb_busiffn_getusbdi_version">GetUSBDIVersion</a> function to report its output data.


## -struct-fields




### -field USBDI_Version

Contains a binary-coded decimal USB interface version number. Released interface versions are listed in the following table.

<table>
<tr>
<th>Operating system</th>
<th>Interface version</th>
</tr>
<tr>
<td>
Windows 98 Gold

</td>
<td>
0x00000102

</td>
</tr>
<tr>
<td>
Windows 98 SE

</td>
<td>
0x00000200

</td>
</tr>
<tr>
<td>
Windows 2000

</td>
<td>
0x00000300

</td>
</tr>
<tr>
<td>
Windows Millennium Edition

</td>
<td>
0x00000400

</td>
</tr>
<tr>
<td>
Windows XP

</td>
<td>
0x00000500

</td>
</tr>
<tr>
<td>
Windows Vista

Windows 7

Windows 8

</td>
<td>
0x00000600

</td>
</tr>
</table>
 


### -field Supported_USB_Version

Contains a binary-coded decimal USB specification version number. 


## -remarks




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/nc-usbbusif-pusb_busiffn_getusbdi_version">GetUSBDIVersion</a> is deprecated in Windows 8 and later versions of the operating system. To determine whether a particular  version is supported by the underlying USB driver stack, the client driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbdlib/nf-usbdlib-usbd_isinterfaceversionsupported">USBD_IsInterfaceVersionSupported</a>.  




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbbusif/nc-usbbusif-pusb_busiffn_getusbdi_version">GetUSBDIVersion</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff540046(v=vs.85)">USB Bus Driver Interface (USBDI) Routines</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">USB Structures</a>
 

 


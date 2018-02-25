---
UID: NS:usb._USBD_VERSION_INFORMATION
title: "_USBD_VERSION_INFORMATION"
author: windows-driver-content
description: The USBD_VERSION_INFORMATION structure is used by the GetUSBDIVersion function to report its output data.
old-location: buses\usbd_version_information.htm
old-project: UsbRef
ms.assetid: 37dc1e94-18cb-48d5-81a2-74d03cef4d5d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUSBD_VERSION_INFORMATION, ,, A, B, D, E, F, I, M, N, O, P, PUSBD_VERSION_INFORMATION, PUSBD_VERSION_INFORMATION structure pointer [Buses], R, S, T, U, USBD_VERSION_INFORMATION, USBD_VERSION_INFORMATION structure [Buses], V, _, _USBD_VERSION_INFORMATION, buses.usbd_version_information, usb/PUSBD_VERSION_INFORMATION, usb/USBD_VERSION_INFORMATION, usbstrct_2871bd56-3ee1-48ab-8353-d19b74470ff1.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usb.h
apiname:
-	USBD_VERSION_INFORMATION
product: Windows
targetos: Windows
req.typenames: USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION
req.product: Windows 10 or later.
---

# _USBD_VERSION_INFORMATION structure


## -description


The <b>USBD_VERSION_INFORMATION</b> structure is used by the <a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a> function to report its output data.


## -syntax


````
typedef struct _USBD_VERSION_INFORMATION {
  ULONG USBDI_Version;
  ULONG Supported_USB_Version;
} USBD_VERSION_INFORMATION, *PUSBD_VERSION_INFORMATION;
````


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




<a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a> is deprecated in Windows 8 and later versions of the operating system. To determine whether a particular  version is supported by the underlying USB driver stack, the client driver must call <a href="..\usbdlib\nf-usbdlib-usbd_isinterfaceversionsupported.md">USBD_IsInterfaceVersionSupported</a>.  




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="https://msdn.microsoft.com/1b571ee0-d47f-40b6-8beb-d57b49ae3ac8">USB Bus Driver Interface (USBDI) Routines</a>



<a href="https://msdn.microsoft.com/05a22049-5165-41a3-aa6f-134c5d1b6c15">GetUSBDIVersion</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBD_VERSION_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


---
UID: NE:sti._STI_DEVICE_MJ_TYPE
title: "_STI_DEVICE_MJ_TYPE"
author: windows-driver-content
description: The STI_DEVICE_TYPE type identifies the device type of a still image device.The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype.
old-location: image\sti_device_type.htm
tech.root: image
ms.assetid: f5ab3aa3-c24e-4716-b94a-525c6b6776dc
ms.date: 05/03/2018
ms.keywords: STI_DEVICE_MJ_TYPE, STI_DEVICE_MJ_TYPE enumeration [Imaging Devices], STI_DEVICE_TYPE, STI_DEVICE_TYPE enumeration [Imaging Devices], StiDeviceTypeDefault, StiDeviceTypeDigitalCamera, StiDeviceTypeScanner, StiDeviceTypeStreamingVideo, _STI_DEVICE_MJ_TYPE, image.sti_device_type, sti/STI_DEVICE_TYPE, sti/StiDeviceTypeDefault, sti/StiDeviceTypeDigitalCamera, sti/StiDeviceTypeScanner, sti/StiDeviceTypeStreamingVideo, stifnc_1cbf2c9f-0c97-439a-8503-c07c68b7d947.xml
ms.topic: enum
req.header: sti.h
req.include-header: Sti.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Sti.h
api_name:
-	STI_DEVICE_MJ_TYPE
product:
- Windows
targetos: Windows
req.typenames: STI_DEVICE_MJ_TYPE
---

# _STI_DEVICE_MJ_TYPE enumeration


## -description


The STI_DEVICE_TYPE type identifies the device type of a still image device.

The DWORD is divided into a HIWORD containing the major device type, and a LOWORD containing a vendor-defined subtype.


## -enum-fields




### -field StiDeviceTypeDefault

Default type.


### -field StiDeviceTypeScanner

Scanner.


### -field StiDeviceTypeDigitalCamera

Digital camera.


### -field StiDeviceTypeStreamingVideo

Streaming video.


## -remarks



The following macros are used to extract the major device type and subtype:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GET_STIDEVICE_TYPE(dwDevType)
GET_STIDEVICE_SUBTYPE(dwDevType)</pre>
</td>
</tr>
</table></span></div>



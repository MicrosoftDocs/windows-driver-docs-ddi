---
UID: NS:sti._STINOTIFY
title: "_STINOTIFY"
author: windows-driver-content
description: The STINOTIFY structure is used as a parameter to the IStillImage::LaunchApplicationForDevice, IStiDevice::GetLastNotificationData, and IStiUSD::GetNotificationData methods.
old-location: image\stinotify.htm
old-project: image
ms.assetid: 7dc42f9a-2e55-4ae5-a951-7d1d3b14564b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPSTINOTIFY, LPSTINOTIFY, LPSTINOTIFY structure pointer [Imaging Devices], STINOTIFY, STINOTIFY structure [Imaging Devices], _STINOTIFY, image.stinotify, sti/LPSTINOTIFY, sti/STINOTIFY, stifnc_2cee63fa-a7a5-4a15-be83-e536a504bcb7.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	sti.h
api_name:
-	STINOTIFY
product: Windows
targetos: Windows
req.typenames: STINOTIFY, *LPSTINOTIFY
req.product: Windows 10 or later.
---

# _STINOTIFY structure


## -description


The STINOTIFY structure is used as a parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543796">IStillImage::LaunchApplicationForDevice</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff543751">IStiDevice::GetLastNotificationData</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff543821">IStiUSD::GetNotificationData</a> methods.


## -struct-fields




### -field dwSize

Caller-supplied size, in bytes, of the STINOTIFY structure.


### -field guidNotificationCode

GUID of the event. For more information, see <a href="https://msdn.microsoft.com/5f9be89c-8442-4894-b2f6-a4d3558464bf">Still Image Device Events</a>.


### -field abNotificationData

Byte array containing optional, vendor-defined information.


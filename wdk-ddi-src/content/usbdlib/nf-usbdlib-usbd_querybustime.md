---
UID: NF:usbdlib.USBD_QueryBusTime
title: USBD_QueryBusTime function
author: windows-driver-content
description: The USBD_QueryBusTime routine has been deprecated in Windows XP and later operating systems. Do not use.
old-location: buses\usbd_querybustime.htm
old-project: usbref
ms.assetid: ae59daf6-da7b-4b04-bb5c-dfd353b937a0
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , B, D, Q, S, T, U, USBD_QueryBusTime, USBD_QueryBusTime routine [Buses], _, buses.usbd_querybustime, e, i, m, r, s, u, usbdlib/USBD_QueryBusTime, usbfunc_2911ce15-3106-4c66-95c8-52ff57318131.xml, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Deprecated.
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
req.lib: Usbd.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbd.lib
-	Usbd.dll
apiname:
-	USBD_QueryBusTime
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_QueryBusTime function


## -description


The <b>USBD_QueryBusTime</b> routine has been deprecated in Windows XP and later operating systems. Do not use. 

See URB_FUNCTION_GET_CURRENT_FRAME_NUMBER for equivalent functionality that is supported on all versions of Windows.


## -syntax


````
void USBD_QueryBusTime(
  _In_  PDEVICE_OBJECT RootHubPdo,
  _Out_ PULONG         CurrentFrame
);
````


## -parameters




### -param RootHubPdo [in]

Obsolete.




### -param CurrentFrame [out]

Obsolete.




## -returns



This routine does not return a value.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



<a href="..\usb\ns-usb-_urb_get_current_frame_number.md">URB_GET_CURRENT_FRAME_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_QueryBusTime routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


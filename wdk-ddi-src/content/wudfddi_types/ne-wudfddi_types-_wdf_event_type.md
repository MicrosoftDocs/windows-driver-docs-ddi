---
UID: NE:wudfddi_types._WDF_EVENT_TYPE
title: "_WDF_EVENT_TYPE"
author: windows-driver-content
description: The WDF_EVENT_TYPE enumeration specifies.
old-location: wdf\wdf_event_type.htm
old-project: wdf
ms.assetid: DC6353BB-98C0-4647-9180-F099CD95348E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_EVENT_TYPE, WDF_EVENT_TYPE enumeration, WdfEventBroadcast, WdfEventMaximum, WdfEventReserved, _WDF_EVENT_TYPE, wdf.wdf_event_type, wdfdevice/WDF_EVENT_TYPE, wdfdevice/WdfEventBroadcast, wdfdevice/WdfEventMaximum, wdfdevice/WdfEventReserved, wudfddi_types/WDF_EVENT_TYPE, wudfddi_types/WdfEventBroadcast, wudfddi_types/WdfEventMaximum, wudfddi_types/WdfEventReserved
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
-	wudfddi_types.h
api_name:
-	WDF_EVENT_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_EVENT_TYPE
req.product: Windows 10 or later.
---

# _WDF_EVENT_TYPE enumeration


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WDF_EVENT_TYPE</b> enumeration specifies  types of events about which a driver can notify a registered application.


## -syntax


````
typedef enum _WDF_EVENT_TYPE { 
  WdfEventReserved   = 0,
  WdfEventBroadcast  = 1,
  WdfEventMaximum    = 2
} WDF_EVENT_TYPE;
````


## -enum-fields




### -field WdfEventReserved

Reserved for system use.


### -field WdfEventBroadcast

In the current version of UMDF, the driver must specify <b>WdfEventBroadcast</b>. For more information, see <a href="..\wdfdevice\nf-wdfdevice-wdfdevicepostevent.md">WdfDevicePostEvent</a>.


### -field WdfEventMaximum

Reserved for system use.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558835">IWDFDevice::PostEvent</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicepostevent.md">WdfDevicePostEvent</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_EVENT_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


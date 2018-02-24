---
UID: NS:ucxusbdevice._USBDEVICE_HUB_INFO
title: "_USBDEVICE_HUB_INFO"
author: windows-driver-content
description: Contains parameters for a request to get information about the specified hub. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_HUB_INFO callback function.
old-location: buses\_usbdevice_hub_info.htm
old-project: UsbRef
ms.assetid: F403179A-B339-432D-AAF9-E7D9965F8B00
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PUSBDEVICE_HUB_INFO, buses._usbdevice_hub_info, P_USBDEVICE_HUB_INFO structure pointer [Buses], P_USBDEVICE_HUB_INFO, _USBDEVICE_HUB_INFO, ucxusbdevice/_USBDEVICE_HUB_INFO, ucxusbdevice/P_USBDEVICE_HUB_INFO, USBDEVICE_HUB_INFO structure [Buses], USBDEVICE_HUB_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	ucxusbdevice.h
apiname:
-	USBDEVICE_HUB_INFO
product: Windows
targetos: Windows
req.typenames: USBDEVICE_HUB_INFO, *PUSBDEVICE_HUB_INFO
req.product: Windows 10 or later.
---

# _USBDEVICE_HUB_INFO structure


## -description


Contains parameters for a request to get information about the specified hub. This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_hub_info.md">EVT_UCX_USBDEVICE_HUB_INFO</a> callback function.


## -syntax


````
typedef struct _USBDEVICE_HUB_INFO {
#if __cplusplus
  USBDEVICE_MGMT_HEADER Header;
#else 
  USBDEVICE_MGMT_HEADER ;
#endif 
  ULONG                 NumberOfPorts;
  ULONG                 NumberOfTTs;
  ULONG                 TTThinkTime;
} USBDEVICE_HUB_INFO, *P_USBDEVICE_HUB_INFO;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.


### -field NumberOfPorts

The count of ports available for the USB hub, filled by the client driver.


### -field NumberOfTTs

The count of TT hubs, filled by the client driver.


### -field TTThinkTime

The ThinkTime property of the TT hub, filled by the client driver.


## -see-also

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_hub_info.md">EVT_UCX_USBDEVICE_HUB_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20USBDEVICE_HUB_INFO structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


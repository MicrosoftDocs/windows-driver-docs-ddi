---
UID: NS:ucxendpoint._ENDPOINTS_CONFIGURE
title: "_ENDPOINTS_CONFIGURE"
author: windows-driver-content
description: Describes endpoints to enable or disable endpoints. This structure is passed by UCX in the EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function.
old-location: buses\_endpoints_configure.htm
old-project: usbref
ms.assetid: C24B7D85-AEA9-43B3-9BEE-262CAA255834
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ENDPOINTS_CONFIGURE structure [Buses], P_ENDPOINTS_CONFIGURE, ENDPOINTS_CONFIGURE, P_ENDPOINTS_CONFIGURE structure pointer [Buses], _ENDPOINTS_CONFIGURE, ucxendpoint/P_ENDPOINTS_CONFIGURE, buses._endpoints_configure, ucxendpoint/_ENDPOINTS_CONFIGURE, *PENDPOINTS_CONFIGURE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
-	ucxendpoint.h
apiname:
-	ENDPOINTS_CONFIGURE
product: Windows
targetos: Windows
req.typenames: ENDPOINTS_CONFIGURE, *PENDPOINTS_CONFIGURE
req.product: Windows 10 or later.
---

# _ENDPOINTS_CONFIGURE structure


## -description


Describes   endpoints to enable or disable endpoints. This structure is passed by UCX in the <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a>  callback function.


## -syntax


````
typedef struct _ENDPOINTS_CONFIGURE {
#if _cplusplus
  USBDEVICE_MGMT_HEADER             Header;
#else 
  USBDEVICE_MGMT_HEADER             ;
#endif 
  ULONG                             EndpointsToEnableCount;
  UCXENDPOINT                       *EndpointsToEnable;
  ULONG                             EndpointsToDisableCount;
  UCXENDPOINT                       *EndpointsToDisable;
  ULONG                             EndpointsEnabledAndUnchangedCount;
  UCXENDPOINT                       *EndpointsEnabledAndUnchanged;
  ENDPOINTS_CONFIGURE_FAILURE_FLAGS FailureFlags;
  ULONG                             ExitLatencyDelta;
  UCHAR                             ConfigurationValue;
  UCHAR                             InterfaceNumber;
  UCHAR                             AlternateSetting;
} ENDPOINTS_CONFIGURE, *P_ENDPOINTS_CONFIGURE;
````


## -struct-fields




### -field Header

A <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_mgmt_header.md">USBDEVICE_MGMT_HEADER</a> structure that stores handles to the USB hub or device whose endpoints.


### -field EndpointsToEnableCount

The number of endpoints to configure.


### -field EndpointsToEnable

A pointer to the first endpoint handle in the array of endpoints to  enable.


### -field EndpointsToDisableCount

The number of endpoints to configure.


### -field EndpointsToDisable

A pointer to the first endpoint handle in the array of endpoints to  enable.


### -field EndpointsEnabledAndUnchangedCount

The number of endpoints that were enabled and unchanged.


### -field EndpointsEnabledAndUnchanged

A pointer to the first endpoint handle in the array of endpoints that have not been changed.


### -field FailureFlags

The errors, if any, that might occur when attempting to configure endpoints for the USB device or hub.


### -field ExitLatencyDelta

The Exit Latency Delta (ELD) value. For more information see section 4.6.6.1 of the eXtensible Host Controller Interface specification.


### -field ConfigurationValue

The configuration number of the USB configuration that contains the endpoints. 


### -field InterfaceNumber

The interface number of the USB interface that contains the endpoints. 


### -field AlternateSetting

The setting number of the alternate setting that contains the endpoints. 


### -field Reserved1

 


### -field Reserved2

 



## -see-also

<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20ENDPOINTS_CONFIGURE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


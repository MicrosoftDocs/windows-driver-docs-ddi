---
UID: NS:ucxendpoint._ENDPOINTS_CONFIGURE_FAILURE_FLAGS
title: "_ENDPOINTS_CONFIGURE_FAILURE_FLAGS"
author: windows-driver-content
description: This structure provides failure flags to indicate errors, if any, that might have occurred during a request to an EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function.
old-location: buses\_endpoints_configure_failure_flags.htm
old-project: usbref
ms.assetid: D605A20B-3747-458E-BA9D-F723F884F130
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure pointer [Buses], P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS, ENDPOINTS_CONFIGURE_FAILURE_FLAGS, buses._endpoints_configure_failure_flags, _ENDPOINTS_CONFIGURE_FAILURE_FLAGS, ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure [Buses], ucxendpoint/_ENDPOINTS_CONFIGURE_FAILURE_FLAGS, ucxendpoint/P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS
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
-	ENDPOINTS_CONFIGURE_FAILURE_FLAGS
product: Windows
targetos: Windows
req.typenames: ENDPOINTS_CONFIGURE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure


## -description


This structure provides failure flags to indicate errors, if any, that might have occurred during a request to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a> callback function.


## -syntax


````
typedef struct _ENDPOINTS_CONFIGURE_FAILURE_FLAGS {
  ULONG InsufficientBandwidth  :1;
  ULONG InsufficientHardwareResourcesForEndpoints  :1;
  ULONG MaxExitLatencyTooLarge  :1;
  ULONG Reserved  :29;
} ENDPOINTS_CONFIGURE_FAILURE_FLAGS, *P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS;
````


## -struct-fields




### -field InsufficientBandwidth

Insufficient bandwidth to configure the specified endpoints.


### -field InsufficientHardwareResourcesForEndpoints

Insufficient hardware resources to configure the specified endpoints.


### -field MaxExitLatencyTooLarge

The maximum exit latency is too large to configure the specified endpoints.


### -field Reserved

Do not use.


## -see-also

<a href="..\ucxendpoint\ns-ucxendpoint-_endpoints_configure.md">ENDPOINTS_CONFIGURE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


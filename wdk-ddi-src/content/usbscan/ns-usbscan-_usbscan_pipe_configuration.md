---
UID: NS:usbscan._USBSCAN_PIPE_CONFIGURATION
title: "_USBSCAN_PIPE_CONFIGURATION"
author: windows-driver-content
description: The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to DeviceIoControl, when the specified I/O control code is IOCTL_GET_PIPE_CONFIGURATION.
old-location: image\usbscan_pipe_configuration.htm
old-project: image
ms.assetid: c9b0247b-1444-46c9-a430-897594f8d223
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: PUSBSCAN_PIPE_CONFIGURATION structure pointer [Imaging Devices], *PUSBSCAN_PIPE_CONFIGURATION, USBSCAN_PIPE_CONFIGURATION structure [Imaging Devices], usbscan/USBSCAN_PIPE_CONFIGURATION, usbscan/PUSBSCAN_PIPE_CONFIGURATION, image.usbscan_pipe_configuration, _USBSCAN_PIPE_CONFIGURATION, stifnc_b18d3edd-f392-4b68-82e4-10f870c18f6a.xml, PUSBSCAN_PIPE_CONFIGURATION, USBSCAN_PIPE_CONFIGURATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbscan.h
req.include-header: Usbscan.h
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
-	usbscan.h
apiname:
-	USBSCAN_PIPE_CONFIGURATION
product: Windows
targetos: Windows
req.typenames: USBSCAN_PIPE_CONFIGURATION, *PUSBSCAN_PIPE_CONFIGURATION
req.product: Windows 10 or later.
---

# _USBSCAN_PIPE_CONFIGURATION structure


## -description


The USBSCAN_PIPE_CONFIGURATION structure is used as a parameter to <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a>, when the specified I/O control code is <a href="..\usbscan\ni-usbscan-ioctl_get_pipe_configuration.md">IOCTL_GET_PIPE_CONFIGURATION</a>.


## -syntax


````
typedef struct _USBSCAN_PIPE_CONFIGURATION {
  ULONG                    NumberOfPipes;
  USBSCAN_PIPE_INFORMATION PipeInfo[MAX_NUM_PIPES];
} USBSCAN_PIPE_CONFIGURATION, *PUSBSCAN_PIPE_CONFIGURATION;
````


## -struct-fields




### -field NumberOfPipes

The number of transfer pipes supported for the device.


### -field PipeInfo

Pointer to a <b>NumberOfPipes</b>-sized array of <a href="..\usbscan\ns-usbscan-_usbscan_pipe_information.md">USBSCAN_PIPE_INFORMATION</a> structures.


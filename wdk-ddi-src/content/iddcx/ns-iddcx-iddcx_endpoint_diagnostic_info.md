---
UID: NS:iddcx.IDDCX_ENDPOINT_DIAGNOSTIC_INFO
title: IDDCX_ENDPOINT_DIAGNOSTIC_INFO
author: windows-driver-content
description: Gives information about the video data endpoint.
old-location: display\iddcx_endpoint_diagnostic_info.htm
old-project: display
ms.assetid: 70be09ed-5633-464b-b311-f671efe83a54
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure [Display Devices], IDDCX_ENDPOINT_DIAGNOSTIC_INFO, iddcx/IDDCX_ENDPOINT_DIAGNOSTIC_INFO, display.iddcx_endpoint_diagnostic_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
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
-	iddcx.h
apiname:
-	IDDCX_ENDPOINT_DIAGNOSTIC_INFO
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure


## -description


Gives information about the video data endpoint.


## -syntax


````
typedef struct IDDCX_ENDPOINT_DIAGNOSTIC_INFO {
  UINT                         Size;
  IDDCX_TRANSMISSION_TYPE      TransmissionType;
  PCWSTR                       pEndPointFriendlyName;
  PCWSTR                       pEndPointModelName;
  PCWSTR                       pEndPointManufacturerName;
  IDDCX_ENDPOINT_VERSION*      pHardwareVersion;
  IDDCX_ENDPOINT_VERSION*      pFirmwareVersion;
  IDDCX_FEATURE_IMPLEMENTATION GammaSupport;
} IDDCX_ENDPOINT_DIAGNOSTIC_INFO, *IDDCX_ENDPOINT_DIAGNOSTIC_INFO;
````


## -struct-fields




### -field Size


                     
                 Total size of the structure.


### -field TransmissionType


                     Describes the type of link the video data is being transmitted over.
                 


### -field pEndPointFriendlyName


                     The friendly name of the endpoint, if one exists. This is applicable if the user can give the device a name and is NULL if a friendly name does not exist.
                 


### -field pEndPointModelName


                     The model name of the endpoint. Must be a non-empty string.
                 


### -field pEndPointManufacturerName


                     The manufacture name of the endpoint. Must be a non-empty string.
                 


### -field pHardwareVersion


                     Pointer to version info for the endpoint hardware.
                 


### -field pFirmwareVersion


                     Pointer to version info for the endpoint firmware.
                 


### -field GammaSupport


                     Indicates how gamma is implemented.
                 


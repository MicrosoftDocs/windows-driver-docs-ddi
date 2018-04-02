---
UID: NS:iddcx.IDDCX_ENDPOINT_DIAGNOSTIC_INFO
title: IDDCX_ENDPOINT_DIAGNOSTIC_INFO
author: windows-driver-content
description: Gives information about the video data endpoint.
old-location: display\iddcx_endpoint_diagnostic_info.htm
old-project: display
ms.assetid: 70be09ed-5633-464b-b311-f671efe83a54
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDDCX_ENDPOINT_DIAGNOSTIC_INFO, IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure [Display Devices], display.iddcx_endpoint_diagnostic_info, iddcx/IDDCX_ENDPOINT_DIAGNOSTIC_INFO
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_ENDPOINT_DIAGNOSTIC_INFO
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_ENDPOINT_DIAGNOSTIC_INFO structure


## -description


Gives information about the video data endpoint.


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
                 


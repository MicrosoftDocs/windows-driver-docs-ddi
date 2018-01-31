---
UID: NS:iddcx.IDDCX_ENDPOINT_VERSION
title: IDDCX_ENDPOINT_VERSION
author: windows-driver-content
description: Gives version information about the video data endpoint.
old-location: display\iddcx_endpoint_version.htm
old-project: display
ms.assetid: ad6220e3-9b6a-4a46-978b-31edfb2c8b9b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_ENDPOINT_VERSION structure [Display Devices], IDDCX_ENDPOINT_VERSION, iddcx/IDDCX_ENDPOINT_VERSION, display.iddcx_endpoint_version
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
-	IDDCX_ENDPOINT_VERSION
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_ENDPOINT_VERSION structure


## -description



                 Gives version information about the video data endpoint.
             


## -syntax


````
typedef struct IDDCX_ENDPOINT_VERSION {
  UINT   Size;
  UINT   MajorVer;
  UINT   MinorVer;
  UINT   Build;
  UINT64 SKU;
} IDDCX_ENDPOINT_VERSION, *IDDCX_ENDPOINT_VERSION;
````


## -struct-fields




#### - Size


                     Total size of the structure.
                 


#### - MajorVer


                     The major version defined by the driver.
                 


#### - MinorVer


                     The minor version defined by the driver.
                 


#### - Build


                     The build number defined by the driver.
                 


#### - SKU


                     The SKU type defined by the driver.
                 


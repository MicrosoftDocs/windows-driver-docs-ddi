---
UID: NS:iddcx.IDDCX_ADAPTER_CAPS
title: IDDCX_ADAPTER_CAPS (iddcx.h)
description: Gives information about the capabilities of the adapter.
old-location: display\iddcx_adapter_caps.htm
tech.root: display
ms.assetid: 3a8610e4-22d5-4732-b4be-846449acb5b1
ms.date: 05/10/2018
keywords: ["IDDCX_ADAPTER_CAPS structure"]
ms.keywords: IDDCX_ADAPTER_CAPS, IDDCX_ADAPTER_CAPS structure [Display Devices], display.iddcx_adapter_caps, iddcx/IDDCX_ADAPTER_CAPS
f1_keywords:
 - "iddcx/IDDCX_ADAPTER_CAPS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- iddcx.h
api_name:
- IDDCX_ADAPTER_CAPS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_ADAPTER_CAPS structure


## -description


Gives information about the capabilities of the adapter.
             


## -struct-fields




### -field Size


                     Total size of the structure
                 


### -field Flags


                     Adapter flags utilized by the driver.


### -field MaxDisplayPipelineRate


                      This value represents the total display bandwidth for the adapter. Each mode the driver reports to the OS also has a display pipeline rate associated with it and the OS ensures that the combined display pipeline rate of all the active modes will never exceed this value. The driver decides how many units it uses.
                 
                 


### -field MaxMonitorsSupported


                     Indicates the maximum number of monitors that can be connected at the same time.


### -field EndPointDiagnostics

Endpoint diagnostics information. None of this is used for runtime OS decision, but it is used for telemetry.


### -field StaticDesktopReencodeFrameCount


                     The number of frames to request after the desktop goes idle if the driver's encoder requires multiple frames to continue improving quality.
                 


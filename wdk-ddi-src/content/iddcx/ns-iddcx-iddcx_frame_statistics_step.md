---
UID: NS:iddcx.IDDCX_FRAME_STATISTICS_STEP
title: IDDCX_FRAME_STATISTICS_STEP
author: windows-driver-content
description: Gives information about the frame processing step being used by the driver.
old-location: display\iddcx_frame_statistics_step.htm
old-project: display
ms.assetid: a0d1f5b3-d527-417e-8d93-26d8277b7f12
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_FRAME_STATISTICS_STEP structure [Display Devices], IDDCX_FRAME_STATISTICS_STEP structure structure [Display Devices], IDDCX_FRAME_STATISTICS_STEP, iddcx/IDDCX_FRAME_STATISTICS_STEP, display.iddcx_frame_statistics_step, IDDCX_FRAME_STATISTICS_STEP structure, IDDCX_FRAME_STATISTICS_STEP structure pointer [Display Devices]
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
-	IDDCX_FRAME_STATISTICS_STEP
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS_STEP structure


## -description



                 Gives information about the frame processing step being used by the driver.


## -syntax


````
typedef struct IDDCX_FRAME_STATISTICS_STE {
  UINT                             Size;
  IDDCX_FRAME_STATISTICS_STEP_TYPE Type;
  UINT64                           QpcTime;
  UINT32                           Data;
} IDDCX_FRAME_STATISTICS_STEP, *IDDCX_FRAME_STATISTICS_STEP;
````


## -struct-fields




#### - Size


                     Total size of the structure
                 


#### - Type


                     The type of frame processing step
                 


#### - QpcTime


                     Provides the system QPC time of the step
                 


#### - Data


                     When driver defined processing part is used, then the driver can store additional data here
                 


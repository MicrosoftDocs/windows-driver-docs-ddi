---
UID: NS:iddcx.IDDCX_FRAME_STATISTICS_STEP
title: IDDCX_FRAME_STATISTICS_STEP
author: windows-driver-content
description: Gives information about the frame processing step being used by the driver.
old-location: display\iddcx_frame_statistics_step.htm
tech.root: display
ms.assetid: a0d1f5b3-d527-417e-8d93-26d8277b7f12
ms.date: 05/10/2018
ms.keywords: IDDCX_FRAME_STATISTICS_STEP, IDDCX_FRAME_STATISTICS_STEP structure, IDDCX_FRAME_STATISTICS_STEP structure [Display Devices], IDDCX_FRAME_STATISTICS_STEP structure pointer [Display Devices], IDDCX_FRAME_STATISTICS_STEP structure structure [Display Devices], display.iddcx_frame_statistics_step, iddcx/IDDCX_FRAME_STATISTICS_STEP
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
-	IDDCX_FRAME_STATISTICS_STEP
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS_STEP structure


## -description



                 Gives information about the frame processing step being used by the driver.


## -struct-fields




### -field Size


                     Total size of the structure
                 


### -field Type


                     The type of frame processing step
                 


### -field QpcTime


                     Provides the system QPC time of the step
                 


### -field Data


                     When driver defined processing part is used, then the driver can store additional data here
                 


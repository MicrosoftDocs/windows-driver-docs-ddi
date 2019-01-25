---
UID: NE:iddcx.IDDCX_FRAME_STATISTICS_STEP_TYPE
title: IDDCX_FRAME_STATISTICS_STEP_TYPE (iddcx.h)
description: Defines the type of frame processing step.
old-location: display\iddcx_frame_statistics_step_type.htm
tech.root: display
ms.assetid: 1c58841b-fff9-4419-b001-bce150b0f7a0
ms.date: 05/10/2018
ms.keywords: IDDCX_FRAME_STATISTICS_STEP_TYPE, IDDCX_FRAME_STATISTICS_STEP_TYPE enumeration [Display Devices], IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8, IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END, IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START, IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED, display.iddcx_frame_statistics_step_type, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START, iddcx/IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED
ms.topic: enum
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
-	IDDCX_FRAME_STATISTICS_STEP_TYPE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS_STEP_TYPE enumeration


## -description



                     Defines the type of frame processing step.
                


## -enum-fields




### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_FRAME_STATISTICS_STEP_TYPE</b> variable has not yet been assigned a meaningful value.


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_START


                        Used to mark the start of a color convert operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_COLOR_CONVERT_END


                        Used to mark the end of a color convert operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_START


                        Used to mark the start of a encode operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCODE_END


                        Used to mark the end of a encode operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_START


                        Used to mark the start of a encrypt operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_ENCRYPT_END


                        Used to mark the end of a encrypt operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_START


                        Used to mark the start of a mux'ing operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_MUX_END


                        Used to mark the end of a mux'ing operation
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_1


                        Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_2


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_3


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_4


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_5


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_6


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_7


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_8

Driver defined processing step
                        
                    


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_9


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_10


                        
                    Driver defined processing step


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_256


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_1


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_1


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_2


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_2


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_3


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_3


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_START_INTERVAL_256


### -field IDDCX_FRAME_STATISTICS_STEP_TYPE_DRIVER_DEFINED_END_INTERVAL_256


### -field UINT




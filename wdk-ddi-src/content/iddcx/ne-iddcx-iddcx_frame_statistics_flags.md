---
UID: NE:iddcx.IDDCX_FRAME_STATISTICS_FLAGS
title: IDDCX_FRAME_STATISTICS_FLAGS
author: windows-driver-content
description: Indicates whether a frame was altered by the driver.
old-location: display\iddcx_frame_statistics_flags.htm
old-project: display
ms.assetid: 85ae47d8-228c-4fff-9be0-bf56868b9319
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IDDCX_FRAME_STATISTICS_FLAGS, IDDCX_FRAME_STATISTICS_FLAGS enumeration [Display Devices], IDDCX_FRAME_STATISTICS_FLAGS_NONE, IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY, display.iddcx_frame_statistics_flags, iddcx/IDDCX_FRAME_STATISTICS_FLAGS, iddcx/IDDCX_FRAME_STATISTICS_FLAGS_NONE, iddcx/IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_FRAME_STATISTICS_FLAGS
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS_FLAGS enumeration


## -description



                    
                Indicates whether a frame was altered by the driver.


## -enum-fields




### -field IDDCX_FRAME_STATISTICS_FLAGS_NONE


                        
                    Indicates that there are no alterations to the frame.


### -field IDDCX_FRAME_STATISTICS_FLAGS_REDUCED_COLOR_FIDELITY


                        If set indicates that the driver reduced the color fidelity of the desktop image while processing and transmitting this frame.


### -field UINT




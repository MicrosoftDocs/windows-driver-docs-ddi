---
UID: NS:iddcx.IDARG_IN_SETUP_HWCURSOR
title: IDARG_IN_SETUP_HWCURSOR
author: windows-driver-content
description: Gives information about new cursors associated with a monitor.
old-location: display\idarg_in_setup_hwcursor.htm
tech.root: display
ms.assetid: 1e2c959c-0ebd-4464-ad47-96f432cb5c6b
ms.date: 5/10/2018
ms.keywords: IDARG_IN_SETUP_HWCURSOR, IDARG_IN_SETUP_HWCURSOR structure [Display Devices], display.idarg_in_setup_hwcursor, iddcx/IDARG_IN_SETUP_HWCURSOR
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
-	IDARG_IN_SETUP_HWCURSOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_SETUP_HWCURSOR structure


## -description



                 Gives information about new cursors associated with a monitor.


## -struct-fields




### -field CursorInfo


                     [in] Cursor information for this path.
                 


### -field hNewCursorDataAvailable


                     [in] An event handle that will be triggered when new cursor data is available.
                 


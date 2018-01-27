---
UID: NE:iddcx.IDDCX_MONITOR_DESCRIPTION_TYPE
title: IDDCX_MONITOR_DESCRIPTION_TYPE
author: windows-driver-content
description: Used to describe the monitor description.
old-location: display\iddcx_monitor_description_type.htm
old-project: display
ms.assetid: ca50256b-2b37-4d39-ad4c-e2eaaa0adbb1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDDCX_MONITOR_DESCRIPTION_TYPE enumeration [Display Devices], iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED, IDDCX_MONITOR_DESCRIPTION_TYPE, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID, display.iddcx_monitor_description_type, IDDCX_MONITOR_DESCRIPTION_TYPE_EDID, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE, iddcx/IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED
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
req.lib: 
req.dll: 
req.irql: _requires_same_
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	iddcx.h
apiname: 
-	IDDCX_MONITOR_DESCRIPTION_TYPE
product: Windows
targetos: Windows
req.typenames: 
---

# IDDCX_MONITOR_DESCRIPTION_TYPE enumeration


## -description



                     Used to describe the monitor description.
                


## -syntax


````
typedef enum _IDDCX_MONITOR_DESCRIPTION_TYPE { 
  IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED  = 0,
  IDDCX_MONITOR_DESCRIPTION_TYPE_EDID           = 1,
  IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID      = 2
} IDDCX_MONITOR_DESCRIPTION_TYPE;
````


## -enum-fields




### -field IDDCX_MONITOR_DESCRIPTION_TYPE_UNINITIALIZED


                        
                    Indicates that an <b>IDDCX_MONITOR_DESCRIPTION_TYPE</b> variable has not yet been assigned a meaningful value.


### -field IDDCX_MONITOR_DESCRIPTION_TYPE_EDID


                        The monitor description is EdId
                    


### -field IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID_AND_EDID



### -field UINT




#### - IDDCX_MONITOR_DESCRIPTION_TYPE_DISPLAYID


                        The monitor description is DisplayId
                    


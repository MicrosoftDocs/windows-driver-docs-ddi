---
UID: NS:iddcx.IDARG_IN_QUERYTARGETMODES
title: IDARG_IN_QUERYTARGETMODES
author: windows-driver-content
description: Gives information about the target modes associated with a monitor.
old-location: display\idarg_in_querytargetmodes.htm
old-project: display
ms.assetid: 4eeadee1-ac2a-46f5-88e0-fe8d3db3dcf1
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDARG_IN_QUERYTARGETMODES structure [Display Devices], iddcx/IDARG_IN_QUERYTARGETMODES, IDARG_IN_QUERYTARGETMODES, display.idarg_in_querytargetmodes
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
-	IDARG_IN_QUERYTARGETMODES
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_QUERYTARGETMODES structure


## -description


Gives information about the target modes associated with a monitor.


## -syntax


````
typedef struct IDARG_IN_QUERYTARGETMODES {
  IDDCX_MONITOR_DESCRIPTION                                   MonitorDescription;
  UINT                                                        TargetModeBufferInputCount;
  _Field_size_(TargetModeBufferInputCount) IDDCX_TARGET_MODE* pTargetModes;
} IDARG_IN_QUERYTARGETMODES, *IDARG_IN_QUERYTARGETMODES;
````


## -struct-fields




### -field MonitorDescription


                     [in] The monitor description. 

<div class="alert"><b>Note</b>  This may not be the monitor description the driver originally provided in the monitor arrival call, which allows for the monitor description to be updated by the OS.</div>
<div> </div>

### -field TargetModeBufferInputCount


                     [in] The number of target modes the <b>pTargetModes</b> buffer passed to the driver can hold. If the value is zero, then the driver should not copy the target mode list to <b>pTargetModes.</b>


### -field pTargetModes


                     [out] Pointer to the buffer that the driver should copy the target modes it supports for this monitor
                 to.


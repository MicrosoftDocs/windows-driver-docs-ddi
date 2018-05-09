---
UID: NS:iddcx.IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
title: IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
author: windows-driver-content
description: Gives information about the default description modes for the monitor, as well as the preferred mode of the monitor.
old-location: display\idarg_out_getdefaultdescriptionmodes.htm
old-project: display
ms.assetid: 0e172d33-e4af-4345-a979-6b4549565ec7
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IDARG_OUT_GETDEFAULTDESCRIPTIONMODES, IDARG_OUT_GETDEFAULTDESCRIPTIONMODES structure [Display Devices], display.idarg_out_getdefaultdescriptionmodes, iddcx/IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
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
-	IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_GETDEFAULTDESCRIPTIONMODES structure


## -description


Gives information about the default description modes for the monitor, as well as the preferred mode of the monitor.


## -struct-fields




### -field DefaultMonitorModeBufferOutputCount


                     [out] If the <a href="https://msdn.microsoft.com/library/windows/hardware/mt761894">IDARG_IN_PARSEMONITORDESCRIPTION</a> value <b>pDefaultMonitorModes</b> was NULL, then the driver should set this to the number of monitor modes the driver would generate for the specified monitor description.

 If the <a href="https://msdn.microsoft.com/library/windows/hardware/mt761894">IDARG_IN_PARSEMONITORDESCRIPTION</a> value <b>pDefaultMonitorModes</b> was non-NULL, then this is the count of the monitor modes that the driver copied to that buffer.
                 


### -field PreferredMonitorModeIdx


                     [out] Index into the <b>pMonitorModes</b> array of the preferred monitor mode. A value of <b>NO_PREFERRED_MODE</b> indicates that there is no preferred monitor mode.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt761894">IDARG_IN_PARSEMONITORDESCRIPTION</a>
 

 


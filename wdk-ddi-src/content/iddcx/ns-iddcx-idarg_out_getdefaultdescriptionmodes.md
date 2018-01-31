---
UID: NS:iddcx.IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
title: IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
author: windows-driver-content
description: Gives information about the default description modes for the monitor, as well as the preferred mode of the monitor.
old-location: display\idarg_out_getdefaultdescriptionmodes.htm
old-project: display
ms.assetid: 0e172d33-e4af-4345-a979-6b4549565ec7
ms.author: windowsdriverdev
ms.date: 12/29/2017
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iddcx.h
apiname:
-	IDARG_OUT_GETDEFAULTDESCRIPTIONMODES
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_OUT_GETDEFAULTDESCRIPTIONMODES structure


## -description


Gives information about the default description modes for the monitor, as well as the preferred mode of the monitor.


## -syntax


````
typedef struct IDARG_OUT_GETDEFAULTDESCRIPTIONMODES {
  UINT DefaultMonitorModeBufferOutputCount;
  UINT PreferredMonitorModeIdx;
} IDARG_OUT_GETDEFAULTDESCRIPTIONMODES, *IDARG_OUT_GETDEFAULTDESCRIPTIONMODES;
````


## -struct-fields




#### - DefaultMonitorModeBufferOutputCount


                     [out] If the <a href="..\iddcx\ns-iddcx-idarg_in_parsemonitordescription.md">IDARG_IN_PARSEMONITORDESCRIPTION</a> value <b>pDefaultMonitorModes</b> was NULL, then the driver should set this to the number of monitor modes the driver would generate for the specified monitor description.

 If the <a href="..\iddcx\ns-iddcx-idarg_in_parsemonitordescription.md">IDARG_IN_PARSEMONITORDESCRIPTION</a> value <b>pDefaultMonitorModes</b> was non-NULL, then this is the count of the monitor modes that the driver copied to that buffer.
                 


#### - PreferredMonitorModeIdx


                     [out] Index into the <b>pMonitorModes</b> array of the preferred monitor mode. A value of <b>NO_PREFERRED_MODE</b> indicates that there is no preferred monitor mode.


## -see-also

<a href="..\iddcx\ns-iddcx-idarg_in_parsemonitordescription.md">IDARG_IN_PARSEMONITORDESCRIPTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IDARG_OUT_GETDEFAULTDESCRIPTIONMODES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


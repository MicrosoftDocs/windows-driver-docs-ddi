---
UID: NS:iddcx.IDARG_IN_PARSEMONITORDESCRIPTION
title: IDARG_IN_PARSEMONITORDESCRIPTION
author: windows-driver-content
description: Gives information about the monitor description.
old-location: display\idarg_in_parsemonitordescription.htm
old-project: display
ms.assetid: dc3c55e3-ddbe-4f06-b9fb-55696dc07502
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.idarg_in_parsemonitordescription, iddcx/IDARG_IN_PARSEMONITORDESCRIPTION, IDARG_IN_PARSEMONITORDESCRIPTION, IDARG_IN_PARSEMONITORDESCRIPTION structure [Display Devices]
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
-	IDARG_IN_PARSEMONITORDESCRIPTION
product: Windows
targetos: Windows
req.typenames: 
---

# IDARG_IN_PARSEMONITORDESCRIPTION structure


## -description



                 Gives information about the monitor description.
             


## -syntax


````
typedef struct IDARG_IN_PARSEMONITORDESCRIPTION {
  IDDCX_MONITOR_DESCRIPTION                                         MonitorDescription;
  UINT                                                              MonitorModeBufferInputCount;
  _Field_size_opt_(MonitorModeBufferInputCount) IDDCX_MONITOR_MODE* pMonitorModes;
} IDARG_IN_PARSEMONITORDESCRIPTION, *IDARG_IN_PARSEMONITORDESCRIPTION;
````


## -struct-fields




### -field MonitorDescription


                     [in] Monitor description the driver should decode.
                 


### -field MonitorModeBufferInputCount


                     [in] The number of monitor modes the <b>pMonitorModes</b> buffer being passed into the driver can hold. A value of zero indicates that the driver should not copy the monitor mode list into the provided buffer, but should set the output buffer size to the size required.


### -field pMonitorModes


                     [out] Pointer to buffer that the driver should copy the monitor modes to if the value is non-NULL. If value is NULL, then driver should not copy any data and should just set the  <a href="..\iddcx\ns-iddcx-idarg_out_parsemonitordescription.md">IDARG_OUT_PARSEMONITORDESCRIPTION</a> value <b>MonitorModeBufferOutputCount</b> to indicate the size of buffer required to store the modes.


## -see-also

<a href="..\iddcx\ns-iddcx-idarg_out_parsemonitordescription.md">IDARG_OUT_PARSEMONITORDESCRIPTION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IDARG_IN_PARSEMONITORDESCRIPTION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


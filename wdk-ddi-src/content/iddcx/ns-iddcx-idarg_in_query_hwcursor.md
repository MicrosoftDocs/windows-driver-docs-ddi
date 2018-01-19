---
UID: NS:iddcx.IDARG_IN_QUERY_HWCURSOR
title: IDARG_IN_QUERY_HWCURSOR
author: windows-driver-content
description: Gives information about the cursor associated with the monitor.
old-location: display\idarg_in_query_hwcursor.htm
old-project: display
ms.assetid: 293364D0-0614-4780-B5E5-1115F084A8C6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IDARG_IN_QUERY_HWCURSOR,
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
req.alt-api: IDARG_IN_QUERY_HWCURSOR
req.alt-loc: iddcx.h
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
req.typenames: 
---

# IDARG_IN_QUERY_HWCURSOR structure



## -description
Gives information about the cursor associated with the monitor.



## -syntax

````
typedef struct _IDARG_IN_QUERY_HWCURSOR {
  IDDCX_MONITOR_DESCRIPTION                                   MonitorDescription;
  UINT                                                        TargetModeBufferInputCount;
  _Field_size_(TargetModeBufferInputCount) IDDCX_TARGET_MODE* pTargetModes;
} IDARG_IN_QUERY_HWCURSOR, *PIDARG_IN_QUERY_HWCURSOR;
````


## -struct-fields

### -field MonitorDescription


                     [in] The shape id of the last cursor shape the driver received for this monitor. This is compared against the latest shape the OS has. The new shape is only copied to the buffer if the OS version has been updated since the last image driver was        received.
                 


### -field TargetModeBufferInputCount


                     [in] Size of the cursor shape buffer <b>pShapeBuffer</b>


### -field pTargetModes


                     [out] Buffer provided by driver that the OS will copy any new cursor image data into.
                 


## -remarks

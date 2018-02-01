---
UID: NS:winsplp._MONITOREX
title: "_MONITOREX"
author: windows-driver-content
description: The MONITOREX structure is obsolete and supported for compatibility purposes only.
old-location: print\monitorex.htm
old-project: print
ms.assetid: f03f72a8-8dc1-4e27-b89b-1afea16a177a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winsplp/LPMONITOREX, _MONITOREX, LPMONITOREX, MONITOREX, MONITOREX structure [Print Devices], print.monitorex, spoolfnc_4910913b-826e-4947-8186-7737d7b3c3fa.xml, *LPMONITOREX, winsplp/MONITOREX, LPMONITOREX structure pointer [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
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
-	winsplp.h
apiname:
-	MONITOREX
product: Windows
targetos: Windows
req.typenames: "*LPMONITOREX, MONITOREX"
req.product: Windows 10 or later.
---

# _MONITOREX structure


## -description


The MONITOREX structure is obsolete and supported for compatibility purposes only. New print monitors should implement <a href="..\winsplp\nf-winsplp-initializeprintmonitor2.md">InitializePrintMonitor2</a> and <a href="..\winsplp\ns-winsplp-_monitor2.md">MONITOR2</a> so that they can be used with print server clusters.

The MONITOREX structure is used as the return value for a print monitor's <a href="..\winsplp\nf-winsplp-initializeprintmonitor.md">InitializePrintMonitor</a> function.


## -syntax


````
typedef struct _MONITOREX {
  DWORD   dwMonitorSize;
  MONITOR Monitor;
} MONITOREX, *LPMONITOREX;
````


## -struct-fields




### -field dwMonitorSize

Specifies the size, in bytes, of the Monitor <b>member</b>.


### -field Monitor

Is a <a href="..\winsplp\ns-winsplp-_monitor.md">MONITOR</a> structure.


## -remarks


Print monitors are responsible for filling in the MONITOREX and MONITOR structures.



## -see-also

<a href="..\winsplp\ns-winsplp-_monitor.md">MONITOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MONITOREX structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>


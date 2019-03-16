---
UID: NF:winsplp.InitializePrintMonitorUI
title: InitializePrintMonitorUI function (winsplp.h)
description: A port monitor UI DLL's InitializePrintMonitorUI function supplies the print spooler with addresses of DLL functions.
old-location: print\initializeprintmonitorui.htm
tech.root: print
ms.assetid: baa80f8c-68ed-43a3-8c82-79a4388f9ab6
ms.date: 04/20/2018
ms.keywords: InitializePrintMonitorUI, InitializePrintMonitorUI function [Print Devices], print.initializeprintmonitorui, spoolfnc_927446a6-117a-4585-8ce0-9a4b543c4037.xml, winsplp/InitializePrintMonitorUI
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Winsplp.h
api_name:
- InitializePrintMonitorUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# InitializePrintMonitorUI function


## -description


A port monitor UI DLL's <b>InitializePrintMonitorUI</b> function supplies the print spooler with addresses of DLL functions.


## -parameters






#### - void


## -returns



The function should return a pointer to an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a> structure.




## -remarks



Port monitor UI DLLs are required to export an <b>InitializePrintMonitorUI</b> function. The function is called immediately after the DLL is loaded, and is not called again until the DLL is reloaded. Its purposes are to allow the DLL to initialize itself, and to provide the spooler with pointers to internal functions.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551600">InitializePrintMonitor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557541">MONITORUI</a>
 

 


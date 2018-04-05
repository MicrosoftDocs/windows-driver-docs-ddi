---
UID: NC:d3dumddi.PFND3DDDI_LOGSTRINGTABLE
title: PFND3DDDI_LOGSTRINGTABLE
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver log a custom Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\logmarkerstringtable.htm
old-project: display
ms.assetid: DDB42924-5C28-4737-92C1-4FB7A00B09AA
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: LogMarkerStringTable, LogMarkerStringTable callback function [Display Devices], PFND3DDDI_LOGSTRINGTABLE, d3dumddi/LogMarkerStringTable, display.logmarkerstringtable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
api_location:
-	D3dumddi.h
api_name:
-	LogMarkerStringTable
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_LOGSTRINGTABLE callback


## -description


Called by the Microsoft Direct3D runtime to request that the user-mode display driver log a custom Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.


## -parameters




### -param hLog

A handle to the Event Tracing for Windows (ETW) log that is to be written to.


### -param pfnLogStringTableEntryCb

A function pointer to the <a href="https://msdn.microsoft.com/54D1F822-2D82-498D-A50F-A917FA127496">LogMarkerStringTableEntry</a> function that locates a string table entry.


## -returns




      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.




## -remarks



This function is free-threaded.




## -see-also




<a href="https://msdn.microsoft.com/54D1F822-2D82-498D-A50F-A917FA127496">LogMarkerStringTableEntry</a>
 

 


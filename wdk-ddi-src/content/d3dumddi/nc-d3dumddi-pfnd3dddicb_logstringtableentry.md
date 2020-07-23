---
UID: NC:d3dumddi.PFND3DDDICB_LOGSTRINGTABLEENTRY
title: PFND3DDDICB_LOGSTRINGTABLEENTRY (d3dumddi.h)
description: Locates a string table entry that is used by the LogMarkerStringTable function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\logmarkerstringtableentry.htm
tech.root: display
ms.assetid: 54D1F822-2D82-498D-A50F-A917FA127496
ms.date: 05/10/2018
keywords: ["PFND3DDDICB_LOGSTRINGTABLEENTRY callback function"]
ms.keywords: LogMarkerStringTableEntry, LogMarkerStringTableEntry callback function [Display Devices], PFND3DDDICB_LOGSTRINGTABLEENTRY, PFND3DDDICB_LOGSTRINGTABLEENTRY callback, d3dumddi/LogMarkerStringTableEntry, display.logmarkerstringtableentry
f1_keywords:
 - "d3dumddi/LogMarkerStringTableEntry"
 - "LogMarkerStringTableEntry"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3dumddi.h
api_name:
- LogMarkerStringTableEntry
targetos: Windows
req.typenames: 
---

# PFND3DDDICB_LOGSTRINGTABLEENTRY callback function


## -description


Locates a string table entry that is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_logstringtable">LogMarkerStringTable</a> function to log an Event Tracing for Windows (ETW) marker event. Optionally implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.


## -parameters




### -param hLog

A handle to the ETW log that is to be written to. Must be the same <i>hLog</i> handle passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_logstringtable">LogMarkerStringTable</a> function.


### -param StringIndex

The offset, in bytes, of the string table entry pointed to by <b>Info</b>. Can be negative if the string is passed along with the marker event.


### -param Info

A custom text string embedded in the ETW packet. Can be <b>NULL</b>.


## -returns




      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_logstringtable">LogMarkerStringTable</a>
 

 


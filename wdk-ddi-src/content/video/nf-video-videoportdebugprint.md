---
UID: NF:video.VideoPortDebugPrint
title: VideoPortDebugPrint function (video.h)
description: Video miniport drivers should not call the VideoPortDebugPrint function. Instead, they should call the VideoDebugPrint macro.
old-location: display\videoportdebugprint.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortDebugPrint function"]
ms.keywords: VideoPortDebugPrint, VideoPortDebugPrint function [Display Devices], VideoPort_Functions_a98adb70-bb89-4d0d-8922-836056896a61.xml, display.videoportdebugprint, video/VideoPortDebugPrint
req.header: video.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortDebugPrint
 - video/VideoPortDebugPrint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortDebugPrint
---

# VideoPortDebugPrint function


## -description

Video miniport drivers should not call the <b>VideoPortDebugPrint</b> function. Instead, they should call the <a href="/previous-versions/ff570170(v=vs.85)">VideoDebugPrint</a> macro.

## -parameters

### -param DebugPrintLevel

### -param DebugMessage 

[in]
Pointer to a string that contains the debug message.

## -returns

None

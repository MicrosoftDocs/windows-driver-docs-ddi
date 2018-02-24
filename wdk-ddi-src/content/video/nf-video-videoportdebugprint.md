---
UID: NF:video.VideoPortDebugPrint
title: VideoPortDebugPrint function
author: windows-driver-content
description: Video miniport drivers should not call the VideoPortDebugPrint function. Instead, they should call the VideoDebugPrint macro.
old-location: display\videoportdebugprint.htm
old-project: display
ms.assetid: c476c8a2-5d79-45cd-ae72-f8792137f9c2
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.videoportdebugprint, VideoPortDebugPrint function [Display Devices], VideoPortDebugPrint, video/VideoPortDebugPrint, VideoPort_Functions_a98adb70-bb89-4d0d-8922-836056896a61.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortDebugPrint
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortDebugPrint function


## -description


Video miniport drivers should not call the <b>VideoPortDebugPrint</b> function. Instead, they should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570170">VideoDebugPrint</a> macro.


## -syntax


````
VOID VideoPortDebugPrint(
       VIDEO_DEBUG_LEVEL DebugPrintLevel,
  _In_ PSTR              DebugMessage
);
````


## -parameters




### -param DebugPrintLevel


### -param DebugMessage [in]

Pointer to a string that contains the debug message.


### -param param

TBD




## -returns



None




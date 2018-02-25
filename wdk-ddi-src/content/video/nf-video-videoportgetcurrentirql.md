---
UID: NF:video.VideoPortGetCurrentIrql
title: VideoPortGetCurrentIrql function
author: windows-driver-content
description: The VideoPortGetCurrentIrql function gets the current IRQL.
old-location: display\videoportgetcurrentirql.htm
old-project: display
ms.assetid: 04cbc86b-a977-43bd-a736-3a7258c671fd
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , C, G, I, P, V, VideoPortGetCurrentIrql, VideoPortGetCurrentIrql function [Display Devices], VideoPort_Functions_acfcf9f4-819a-4fc5-ae4f-214a78059e7a.xml, d, display.videoportgetcurrentirql, e, i, l, n, o, q, r, t, u, video/VideoPortGetCurrentIrql"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortGetCurrentIrql
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetCurrentIrql function


## -description


The <b>VideoPortGetCurrentIrql</b> function gets the current IRQL.


## -syntax


````
UCHAR VideoPortGetCurrentIrql(void);
````


## -parameters






## -returns



<b>VideoPortGetCurrentIrql</b> returns the current IRQL.




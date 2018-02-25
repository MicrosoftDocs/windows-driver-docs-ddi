---
UID: NF:dmusicks.IPositionNotify.PositionNotify
title: IPositionNotify::PositionNotify method
author: windows-driver-content
description: Byte position notify for MXF graph.
old-location: audio\ipositionnotify_positionnotify.htm
old-project: audio
ms.assetid: 1C29A0B4-E50D-4EA2-95A4-4845BD14C88A
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, I, IPositionNotify, IPositionNotify interface [Audio Devices], PositionNotify method, IPositionNotify::PositionNotify, N, P, PositionNotify method [Audio Devices], PositionNotify method [Audio Devices], IPositionNotify interface, PositionNotify,IPositionNotify.PositionNotify, audio.ipositionnotify_positionnotify, dmusicks/IPositionNotify::PositionNotify, f, i, n, o, s, t, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dmusicks.h
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
req.lib: dmusicks.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dmusicks.h
apiname:
-	IPositionNotify.PositionNotify
product: Windows
targetos: Windows
req.typenames: DMUS_STREAM_TYPE
---

# IPositionNotify::PositionNotify method


## -description


Byte position notify for MXF graph.


## -syntax


````
HRESULT PositionNotify(
  [in] ULONGLONG bytePosition
);
````


## -parameters




### -param bytePosition [in]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\dmusicks\nn-dmusicks-ipositionnotify.md">IPositionNotify</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPositionNotify::PositionNotify method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

